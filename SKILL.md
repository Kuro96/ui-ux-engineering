---
name: universal-ui-ux-engineering
description: Apply these rules when you create, change, or review user interface (UI) code. This skill stops the direct output of backend data structures to the screen and keeps the layout clear.
---

# UI and UX Engineering Rules

Build the user interface for human users, not as a raw view of backend data. Do not map backend data fields directly to screen elements. Obey these five rules when you write UI code.

## 1. Separate Data from the View
Do not show raw backend state, internal configuration, or prompt instructions directly on the screen:
- **Show human-readable text**: Show only short, clear names in dropdown menus, labels, and buttons. Do not show internal IDs, route prefixes, enum keys, or file paths in visible text. Keep internal identifiers in `value` attributes, `data-*` attributes, or background state.
- **Hide secondary data by default**: Separate primary data from secondary metadata. Put secondary parameters, detailed settings, and long text inside collapsible views (such as drawers, popovers, or tooltips). Do not show all data fields on the main screen at the same time.
- **Do not show prompt rules as UI text**: Do not copy business rules or system logic from the prompt into the UI as permanent text. Communicate system rules through disabled states, layout position, or short tooltips on a `?` icon.

## 2. Remove Repeated Information
Reduce extra DOM elements to keep the screen clear:
- **Group common labels**: When you show a list of similar items, put shared titles, units, and notes in one header. Show this shared text only one time. Do not repeat the same static text in each item.
- **Do not put boxes inside boxes**: Do not put a bordered card around each single field or setting row. Put related form items in one shared container. Use empty space or thin lines to separate the items.

## 3. Allocate Screen Space Correctly
Assign screen space by task importance, not by the number of components:
- **Give maximum space to the main work area**: Give the primary work area (such as the main list or canvas) the largest part of the screen. Use `flex: 1` and `min-height: 0` on the main container.
- **Collapse empty areas**: When a secondary panel has no data, hide it or collapse it into one thin bar. Do not show a large empty box that reduces the main work area.
- **Use one scroll bar and one navigation method**:
  - Use only one vertical scroll bar in each view area. Do not put scrollable containers inside other scrollable containers.
  - Do not use a scroll bar and pagination buttons on the same short list.

## 4. Match the Host Theme
Make all new views match the visual style of the host application:
- **Use existing style tokens first**: Before you write styles, find and use the existing CSS variables and theme tokens in the project.
- **Do not hardcode colors**: Do not write fixed color values (such as hex or RGB codes) in component styles. Make all backgrounds, text, and borders inherit the global theme variables.

## 5. Complete These Steps Before You Write Code
Do these three steps before you output UI code:
1. **Filter**: Remove all machine prefixes, enum keys, and internal logic notes from visible UI text.
2. **Combine**: Merge repeated form structures into compact rows or tables, and remove repeated helper text.
3. **Size**: Make sure that empty states or long text strings do not reduce the main work area.
