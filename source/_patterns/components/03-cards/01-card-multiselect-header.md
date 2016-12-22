---
title: Card
---
## Overview

This is a Bootstrap component, [see complete documentation here](http://v4-alpha.getbootstrap.com/components/card/)

## Usage

| Class | Usage |
| -- | -- |
| `.pf-card--select` **Applied to:** `.card` |  **Outcome:** Applies a card border that changes color when selection is active  **Required:** If single- or multi-selection is enabled for the card  |
| `.active` **Applied to:** `.pf-card--select` | **Outcome:** Indicates that the card is selected by applying a blue border to the card **Required:** If the selection state for the card is true |
| `.pf-card--multiselect` **Applied to:** `.card` |  **Outcome:** Alters the card layout to accommodate a checkbox  **Required:** If multi-selection is enabled for the card **Remarks:** Always use it with `.pf-card--select` |
| `.pf-card__checkbox` **Applied to:** parent `label` of `<input type="checkbox">` |  **Outcome:** Positions the checkbox within the card and defines the clickable area of the checkbox  **Required:** If multi-selection is enabled for the card **Remarks:** Always use it with `.pf-card--multiselect`  |
