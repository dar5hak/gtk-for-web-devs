---
theme: default
background: none
class: text-center
highlighter: shiki
aspectRatio: "16/10"
fonts:
  sans: "Inter"
  mono: "Roboto Mono"
info: |
  ## GTK for Web Developers
title: GTK for Web Developers
---

# GTK for Web Developers

---
layout: center
---

<video src="/assets/same-but-different.mp4" autoplay loop />

---

# Languages

Consider your needs. When in doubt, pick Vala.

<div grid="~ cols-2 gap-2" m="-t-2">

Web

GTK

<ul>
  <li>JavaScript</li>
  <li>TypeScript</li>
  <li>Elm</li>
  <li>Dart</li>
</ul>

<ul>
  <li>Vala
    <ul>
      <li>Transpiles to C</li>
      <li>Granite available</li>
    </ul>
  </li>
  <li>Rust</li>
  <li>JavaScript (GJS)</li>
  <li>Python</li>
  <li>C</li>
</ul>

</div>

<!-- node-gtk -->

---

# The “DOM”

Similar hierarchy, different terms

| **Web**   | **GTK**  |
| --------- | -------- |
| Document  | Window   |
| Element   | Widget   |
| Attribute | Property |

---

# Widgets

![A screenshot of Widget Factory, demonstrating numerous GTK widgets](/assets/widget-factory-dark.png)

---

# Manipulating the Tree

<div grid="~ cols-2 gap-2" m="-t-2">

React

GTK

```js
/* JavaScript (transpiled from JSX) */

function App() {
  // return <button disabled>Boop!</button>
  return React.createElement("button", { disabled: true }, "Boop!");
}

ReactDOM.render(<App />, document.getElementById("root"));
```

```csharp
/* Vala */

var button = new Gtk.Button () {
  label = "Boop!",
  sensitive = false
}

var window = new Gtk.Window ();

window.add (button);
```

</div>

<!-- This means it is possible to directly access a lot of unrelated widgets. With great power comes great responsibility. -->

---

# Flexbox Layout

<div grid="~ cols-2 gap-2" m="-t-2">

Web

GTK

```css
.flex {
  display: flex;
  flex-direction: column;
  gap: 4px;
}
```

```csharp
var box = new Gtk.Box (Gtk.Orientation.VERTICAL, 4);
var boxItem = new Gtk.Button ();

box.append (boxItem);

```

</div>

---

# Grid Layout

<div grid="~ cols-2 gap-2" m="-t-2">

Web

GTK

```css
.grid {
  display: grid;
  row-gap: 4px;
  column-gap: 6px;
}

.grid-item {
  grid-area: 2 / 3 / span 4 / span 6;
  justify-self: center;
  align-self: end;
}
```

```csharp
var grid = new Gtk.Grid () {
  row_spacing = 4,
  column_spacing = 6
};

var gridItem = new Gtk.Button () {
  halign = Gtk.Align.CENTER,
  valign = Gtk.Align.END
};

grid.attach (gridItem, 1, 2, 4, 6);

```

</div>

---

# Styling

<div grid="~ cols-2 gap-2" m="-t-2">

Web

GTK

```html
<input type="text" class="flat" />
```

```csharp
var entry = new Gtk.Entry ();

entry.get_style_context ().add_class ("flat");
// or
entry.add_css_class ("flat"); // GTK 4 only
```

```css
:root {
  --color-primary: #b4d455;
}

.flat {
  background: transparent;
  border: none;
  color: var(--color-primary);
  font-weight: bold;
}
```

```css
@define-color color_primary #b4d455;

.flat {
  background: transparent;
  border: none;
  color: @color_primary;
  font-weight: bold;
}
```

</div>

---

# GTK Inspector

```sh
# Enable the inspector
gsettings set org.gtk.Settings.Debug enable-inspector-keybinding true
```

Hit <kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>D</kbd> to launch the inspector.

Hit <kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>I</kbd> to inspect the widget under the mouse pointer.

![GTK Inspector](/assets/inspector.png)

---

# UI Libraries

<div grid="~ cols-2 gap-2" m="-t-2">

Web

GTK

<ul>
  <li>jQuery UI</li>
  <li>Material UI</li>
  <li>Bulma, Bootstrap and friends</li>
</ul>

<ul>
  <li>Granite</li>
  <li>Handy (GTK 3)</li>
  <li>LibAdwaita (GTK 4)</li>
</ul>

</div>

---

# elementary Developer Docs

https://docs.elementary.io/develop/

![elementary Developer Docs landing page](/assets/elementary-dev-docs.png)

---

# GTK CSS Properties

https://docs.gtk.org/gtk4/css-properties.html

![List of GTK CSS Properties](/assets/gtk-css-properties.png)

---

# Vala Tutorial

https://wiki.gnome.org/Projects/Vala/Tutorial

![Vala tutorial](/assets/vala-tutorial.png)

---

# Valadoc

https://valadoc.org/. Stays crunchy. Even in milk.

![Valadoc home page](/assets/valadoc-home.png)

---
layout: center
---

# That’s all, folks!
