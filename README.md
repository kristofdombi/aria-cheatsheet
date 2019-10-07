<p align="center">
  <img alt="ARIA cheatsheet logo" src="logo.jpg" />
</p>

<h1 align="center">ARIA cheatsheet</h1>

<h4 align="center">Curated cheatsheet and examples of accessible, basic web elements.</h4>

## Foreword

We, web developers are responsible for making the Internet more accessible, though we often forget (...or we are just lazy) to implement the features, which would help us to achieve this goal.<br />
Therefore I started to assemble a cheatsheet, which is designed to help developers finding concise information about every major web element's accessibility criteria and copy pastable examples.

## Contributing

TODO

## Table of Contents

- Best practices
- Components

  - [Accordion](#accordion)
  - [Button](#button)
  - Input
  - Textarea
  - Dialog _(Modal)_
  - Switch
  - Menu _(Dropdown)_

---

### Accordion

**HTML:**

```html
<div id="accordion">
  <h3>
    <button
      id="accordion-section-1"
      aria-expanded="true"
      aria-controls="europe"
      aria-disabled="true"
    >
      <span>Europe</span>
      <span class="accordion-icon" />
    </button>
  </h3>
  <div id="europe" role="region" aria-labelledby="accordion-section-1">
    <ul>
      <li>Amsterdam</li>
      <li>Budapest</li>
      <li>Brussels</li>
      <li>London</li>
      <li>Madrid</li>
    </ul>
  </div>
  <h3>
    <button id="accordion-section-2" aria-expanded="false" aria-controls="asia">
      <span>Asia</span>
      <span class="accordion-icon" />
    </button>
  </h3>
  <div id="asia" role="region" aria-labelledby="accordion-section-2" hidden>
    <ul>
      <li>Bangkok</li>
      <li>Hong Kong</li>
      <li>Taipei</li>
      <li>Tokyo</li>
      <li>Shenzen</li>
    </ul>
  </div>
  <h3>
    <button
      id="accordion-section-3"
      aria-expanded="false"
      aria-controls="america"
    >
      <span>America</span>
      <span class="accordion-icon" />
    </button>
  </h3>
  <div id="america" role="region" aria-labelledby="accordion-section-3" hidden>
    <ul>
      <li>Dallas</li>
      <li>Los Angeles</li>
      <li>Mexico</li>
      <li>Rio de Janero</li>
      <li>Washington</li>
    </ul>
  </div>
</div>
```

**Props:**

| Name              | Description                                                                                                                                                                                                                                                       | Values     |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| `role`            | Creates a landmark region that contains the currently expanded accordion panel.                                                                                                                                                                                   | `'region'` |
| `aria-expanded`   | Set to `true` when the accordion panel is expanded, otherwise set to `false`.                                                                                                                                                                                     | `boolean`  |
| `aria-controls`   | Points to the ID of the panel which the header controls.                                                                                                                                                                                                          | `string`   |
| `aria-disabled`   | If the accordion panel is expanded and is not allowed to be collapsed, then set to true.                                                                                                                                                                          | `boolean`  |
| `aria-labelledBy` | <ul><li>Defines the accessible name for the `region` element.</li><li>References the accordion header button that expands and collapses the `region`.</li><li>`region` elements are required to have an accessible name to be identified as a landmark.</li></ul> | `boolean`  |

**Interaction keys:**

| Key                                  | Function                                                                                                                                                                                     |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <kbd>Space</kbd> or <kbd>Enter</kbd> | When focus is on the accordion header of a collapsed section, expands the section.                                                                                                           |
| <kbd>Tab</kbd>                       | Moves focus to the previous focusable element.                                                                                                                                               |
| <kbd>Shift</kbd> + <kbd>Tab</kbd>    | <ul><li>Moves focus to the next focusable element.</li><li>All focusable elements in the accordion are included in the page <kbd>Tab</kbd> sequence.</li></ul>                               |
| <kbd>Down Arrow</kbd>                | <ul><li>When focus is on an accordion header, moves focus to the next accordion header.</li><li>When focus is on last accordion header, moves focus to first accordion header.</li></ul>     |
| <kbd>Up Arrow</kbd>                  | <ul><li>When focus is on an accordion header, moves focus to the previous accordion header.</li><li>When focus is on first accordion header, moves focus to last accordion header.</li></ul> |
| <kbd>Home</kbd>                      | When focus is on an accordion header, moves focus to the first accordion header.                                                                                                             |
| <kbd>End</kbd>                       | When focus is on an accordion header, moves focus to the last accordion header.                                                                                                              |

**Required Javascript features:**

- `onclick`
- `onKeyDown`

[⬆️ Back to top](#table-of-contents) - [📖 Source](https://www.w3.org/TR/wai-aria-practices/examples/accordion/accordion.html)

---

### Button

**HTML:**

```html
<div tabindex="0" role="button">
  Click me!
</div>
```

**Props:**

| Name           | Description                                                          | Values                   |
| :------------- | :------------------------------------------------------------------- | :----------------------- |
| `role`         | The button role identifies an element as a button to screen readers. | `'button'`               |
| `aria-pressed` | Only needed for toggle buttons                                       | `boolean` or `undefined` |
| `aria-label`   | Specify if your button is represented by an icon.                    | `string`                 |

**Interaction keys:**

| Key                                  | Function         |
| ------------------------------------ | ---------------- |
| <kbd>Enter</kbd> or <kbd>Space</kbd> | Activates button |

**Required Javascript features:**

- `onclick`
- `onKeyDown`

[⬆️ Back to top](#table-of-contents) - [📖 Source](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)

---
