---
title: PatternFly Secondary Navigation
---
## Overview

The secondary navigation can be used on it is own but it's usually used with primary horizontal nav or tabs.

## Accessibility
`role="tabpanel"` should be used for the div that wraps the tab contents.

| Attribute | Value | Usage |
| -- | -- | -- |
| `role` **Applied to:** `<nav>` | "navigation" |  **Outcome:** [Refer to this explanation for more details](http://a11yproject.com/posts/aria-landmark-roles/)   **Required:** Yes, until implicit mapping for `<nav>` is fully supported  |
| `role` **Applied to:** `<ul>` | "tablist" |  **Outcome:** Identifies the `<ul>` list as a tablist to assistive device users   **Required:** Yes |
| `role` **Applied to:** `<a>` | "tab" |  **Outcome:** Identifies the `<a>` link as a tab to assistive device users   **Required:** Yes |
| `role` **Applied to:** `<div>` that wraps the tab contents | "tabpanel" |  **Outcome:** Identifies the tab contents to assistive device users   **Required:** Yes  **Note:** And example of this is on the basic template |
| `aria-selected` **Applied to:** `a` | "true" |   **Outcome:** Communicates which page is selected to assistive device users   **Required:** Yes |
| `aria-disabled` **Applied to:** `a` | "true" |   **Outcome:** Communicates which page is disabled to assistive device users   **Required:** Yes |

## Usage

| Class | Usage |
| -- | -- |
| `.pf-secondary-nav` **Applied to:** `ul` |  **Outcome:** Initiates a secondary underline style menu **Required:** Yes **Remarks:** Always use inside a `.nav` and `.nav-tabs` |
| `.pf-secondary-nav__item` **Applied to:** `li` |  **Outcome:** This hook is here to provide a place to style the nav item itself. **Required:** No |
| `.pf-secondary-nav__link` **Applied to:** `a` |  **Outcome:** Gives styles to anchors **Required:** Yes |
| `.is-active` **Applied to:** `a` |  **Outcome:** Generates active state **Required:** No |
| `.is-disabled` **Applied to:** `a` |  **Outcome:** Generates disabled state **Required:** No |
