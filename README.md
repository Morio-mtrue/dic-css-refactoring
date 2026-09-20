# dic-css-refactoring

Component CSS series assignment - CSS refactoring.

Refactored from the `component_css_exercise` starter.

## Problem

The Pancake menu on `menu.html` had to become a single column, without
affecting anything else on that page and without touching the Recommended menu
on `index.html`.

## Approach

`.menu_item` is a shared component used by both menus, so changing its width
directly would have broken the home page. Instead a modifier class is added
alongside `menu_list`, following the `menu_list_recommended` multi-class
pattern the project already uses.

`menu.html`

```html
<ul class="menu_list menu_list_pancake">
```

`css/main.css`

```css
.menu_list_pancake {
  display: block;
}
.menu_list_pancake .menu_item {
  width: 100%;
}
```

That is the whole change: two lines of HTML and one rule. The base
`.menu_list` and `.menu_item` components are untouched.

## Verified in the browser

| | Before | After |
| --- | --- | --- |
| Pancake menu items | 4 items at 49%, 2 per row | 4 items at 100%, 1 per row |
| Recommended menu (index.html) | 2 items at 49%, 1 row | 2 items at 49%, 1 row, same position |

Nothing else on either page moved.
