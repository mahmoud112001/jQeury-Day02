# jQuery UI Assignments

Three standalone HTML assignments demonstrating core jQuery and jQuery UI features. Each file is self-contained — no build step required.

---

## Files

| File | Feature |
|------|---------|
| `task01.html` | Login Modal Dialog |
| `task02.html` | Drag & Drop |
| `task03.html` | Photo Slider, Accordion & Navigation Menu |

---

## Libraries Used

- **jQuery 3.7.1** — DOM manipulation and event handling
- **jQuery UI 1.13.2** — UI widgets (Dialog, Draggable, Droppable, Accordion)

Both are loaded from CDN (no installation needed):

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jqueryui/1.13.2/jquery-ui.min.js"></script>
```

---

## Assignment Details

### Task 01 — Login Modal (`task01.html`)

Opens a modal dialog using `$.dialog()` from jQuery UI.

**Features:**
- Click "Open Login" to open the modal
- Enter a username and click Login — a welcome message appears on the page
- Empty username shows a red border validation error
- Cancel or pressing Escape closes the dialog and resets the form
- "Remember me" checkbox included

**Key jQuery UI widget:** `dialog`

```js
$("#login-dialog").dialog({
  autoOpen: false,
  modal: true,
  buttons: { "Login": function () { ... }, "Cancel": function () { ... } }
});
```

---

### Task 02 — Drag & Drop (`task02.html`)

A draggable ball that must be dropped onto a target zone.

**Features:**
- Drag the blue ball anywhere on the stage
- Drop it on the dashed box — the box turns green and shows a success message
- Drop it anywhere else — the ball snaps back to its original position (`revert: "invalid"`)
- Reset button animates the ball back to the start

**Key jQuery UI widgets:** `draggable`, `droppable`

```js
$("#drag-img").draggable({ revert: "invalid" });

$("#drop-zone").droppable({
  accept: "#drag-img",
  hoverClass: "ui-droppable-hover",
  drop: function (event, ui) { ... }
});
```

---

### Task 03 — Slider, Accordion & Menu (`task03.html`)

A full-page layout combining three separate jQuery features.

**Features:**

1. **Photo Slider (header)**
   - 4 slides that auto-advance every 4 seconds
   - Previous / Next arrow buttons
   - Clickable dot indicators
   - Stops auto-play when manually navigated, then resumes

2. **Sidebar Accordion**
   - Built with `$.accordion()` from jQuery UI
   - 4 collapsible sections: Design, Development, Photography, Travel
   - One section open at a time; collapsible to close all

3. **Horizontal Navigation Menu**
   - Simple `<nav>` with links
   - Clicking a link adds the `.active` class and removes it from others

**Key jQuery UI widget:** `accordion`

```js
$("#accordion").accordion({
  collapsible: true,
  active: 0,
  heightStyle: "content"
});
```

---

## How to Run

No server or build tool needed. Just open any file directly in a browser:

```
Double-click task01.html   (or task02.html / task03.html)
```

Or serve locally with any static server:

```bash
# Python
python -m http.server 8000

# Node.js (if npx available)
npx serve .
```

Then visit `http://localhost:8000` and open the file you want.

---

## Browser Support

Works in all modern browsers (Chrome, Firefox, Edge, Safari). jQuery UI 1.13.2 supports IE 9+ as well, so these assignments are broadly compatible.
