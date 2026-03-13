# Divclass Lightbox

[![npm version](https://img.shields.io/npm/v/@divclass/lightbox.svg)](https://www.npmjs.com/package/@divclass/lightbox)

**Lightweight 32 KB (≈11 KB gzipped), dependency-free lightbox** for images and inline content.  
Supports **smart zoom animations, virtual slides, swipe & drag gestures**, and works on **all modern browsers and touch devices**.

[Live Demo](https://lightbox.divclass.org)

---

## 🌟 Key Features

* **Lightweight — 32 KB (≈11 KB gzipped)**  
  Full-featured lightbox without heavy dependencies.
* **Virtual Slides**  
  Only **3 DOM nodes** exist at a time for optimal performance.
* **Fully Responsive**  
  Works perfectly across desktop, tablet, and mobile devices.
* **Cross-browser & Touch-friendly**  
  Supports modern browsers and touch gestures.
* **Easy Integration**  
  Initialize via **data attributes or selectors**.
* **Smart Zoom From Origin**  
  Smooth animation from thumbnail → full image without predefined image sizes.
* **Swipe & Drag Gestures**  
  Intuitive navigation on touch devices
* **Animated Thumbnails & Data Galleries**  
  Create galleries instantly using `data-gallery`.
* **Inline Content & Nested Modals**  
  Display any HTML content and even open nested modals.
* **Smart Image Preloading**  
  Smooth navigation with optimized image loading.
* **Keyboard Navigation**
* **Global Controls**
  - `DivclassLightbox.closeAll()`
  - `DivclassLightbox.destroyAll()`
* **Customizable Animations**

---

## 🌍 Demo

https://lightbox.divclass.org

---


## 📦 Installation

## Install via npm

```bash
npm install @divclass/lightbox
```

```javascript
import DivclassLightbox from "@divclass/lightbox";
import "@divclass/lightbox/style.css"


new DivclassLightbox("[data-dc-lightbox]")
```

## CDN
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@divclass/lightbox/dist/divclass-lightbox.css">
<script src="https://cdn.jsdelivr.net/npm/@divclass/lightbox/dist/divclass-lightbox.umd.js"></script>

<script>
  new DivclassLightbox('[data-dc-lightbox]');
</script>
```

## ES Modules (browser)

```html
<link rel="stylesheet" href="/path/divclass-lightbox.css">

<script type="module">
  import DivclassLightbox from "/path/divclass-lightbox.esm.js";

  new DivclassLightbox("[data-dc-lightbox]");
</script>
```

## Manual Download

Download the latest release and include the files manually:

```html
<link rel="stylesheet" href="dist/divclass-lightbox.css">

<script src="dist/divclass-lightbox.umd.js"></script>

<script>
  new DivclassLightbox('[data-dc-lightbox]');
</script>
```

---

## 🚀 Quick Start

Add the `data-dc-lightbox` attribute to links that should open in the lightbox.

```html
<a href="image-large.jpg" data-dc-lightbox>
  <img src="image-thumb.jpg" alt="">
</a>
```

Initialize the lightbox with a selector:

```js
import DivclassLightbox from "@divclass/lightbox";
import "@divclass/lightbox/style.css"

new DivclassLightbox("[data-dc-lightbox]")
```

---


## Gallery

Group items into a gallery using the `data-gallery` attribute.

```html
<a href="img1.jpg" data-dc-lightbox data-gallery="gallery1">
  <img src="thumb1.jpg" alt="">
</a>

<a href="img2.jpg" data-dc-lightbox data-gallery="gallery1">
  <img src="thumb2.jpg" alt="">
</a>

<a href="img3.jpg" data-dc-lightbox data-gallery="gallery1">
  <img src="thumb3.jpg" alt="">
</a>
```

---

## Caption

Use `data-caption` to display text or HTML.


```html
<a
  href="image.jpg"
  data-dc-lightbox
  data-caption="Lorem ipsum <p>Custom HTML caption</p>"
>
  <img src="thumb.jpg" alt="">
</a>
```

---

## Inline Content

You can open any HTML element inside the lightbox.


```html
<a href="#modal-content" data-dc-lightbox>
  Open modal
</a>

<div id="modal-content" style="display:none">
  <h2>Hello</h2>
  <p>This content is displayed inside the lightbox.</p>
</div>
```

You can also use `data-src`:
 
```html
<button data-dc-lightbox data-src="#modal-content">
  Open modal
</button>
```

---

## Open via JavaScript

You can also open the lightbox programmatically.

```js
DivclassLightbox.show({
  src: "https://picsum.photos/id/10/800/1000/",
  type: "image",
  caption: "Test image",
});
```

Open inline content:

```js
DivclassLightbox.show({
  src: "#modal-1"
});
```

Example with additional options:

```js
DivclassLightbox.show({
  src: "https://picsum.photos/id/10/800/1000/",
  type: "image",
  caption: "Auto closing example",
  closeExisting: true,
  autoClose: 2000
});
```

---

## ⚙  Options

| Option                 | Type                                                 | Default        | Description                                                                             |
| ---------------------- | ---------------------------------------------------- | -------------- | ------------------------------------------------------                                  |
| icon                   | string                                               | SVG            | Close button icon                                                                       |
| thumbnailsIcon         | string                                               | SVG            | Thumbnails toggle icon                                                                  |
| arrowIcon              | string                                               | SVG            | Arrow navigation icon                                                                   |
| showThumbnailsOnOpen   | boolean                                              | `true`         | Show thumbnails when gallery opens                                                      |
| backdropClick          | "close" \| false                                     | `"close"`      | Close modal when clicking backdrop (inline only)                                        |
| closeExisting          | boolean                                              | `false`        | Closes any currently open lightbox before opening a new one.                            |
| parentContainer        | string                                               | `"body"`       | CSS selector of the container element where the modal will be appended.                 |
| hideScrollbar          | boolean                                              | `true`         | Hide body scrollbar when lightbox is open                                               |
| effect                 | "fadeIn" \| "fadeInDown" \| "fadeInUp" \| "zoomIn"   | `"fadeInUp"`   | Opening animation                                                                       |
| zoomImageFromOrigin    | boolean                                              | `true`         | Animate image from thumbnail position                                                   |
| animationDuration      | number                                               | `400`          | Opening/closing animation duration (ms)                                                 |
| autoClose              | false \| number                                      | `false`        | Automatically close lightbox after specified time (ms)                                  |
| type                   | "inline" \| "image"                                  | `"inline"`     | Default content type                                                                    |
| caption                | string \| false                                      | `false`        | Caption text or HTML                                                                    |
| slideChangeDuration    | number                                               | `280`          | Slide transition duration (ms)                                                          |
| slideOffset            | number                                               | `0.1`          | Distance offset between slides during drag/swipe navigation. Accepts values from 0 to 1 |

---

## HTML Data Attributes

<table>
  <thead>
    <tr>
      <th>Attribute</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="text-nowrap">data-src</code></td>
      <td>
        Alternative source if the element is not a link with <code>href</code>.
        Can point to an inline element (<code>#modal</code>) or an image URL.
      </td>
    </tr>
    <tr>
      <td><code class="text-nowrap">data-close</code></td>
      <td>
        Closes the lightbox when the element is clicked. Useful for custom buttons.
        Can also be <code>data-close="close-all"</code> to close all previously opened lightboxes.
      </td>
    </tr>
    <tr>
      <td><code class="text-nowrap">data-type</code></td>
      <td>
        Content type: <code>"image"</code> or <code>"inline"</code>.
        Required if the <code>href</code> for an image has no extension.
      </td>
    </tr>
    <tr>
      <td><code class="text-nowrap">data-caption</code></td>
      <td>
        Caption for the image. Can include HTML tags.
      </td>
    </tr>
    <tr>
      <td><code class="text-nowrap">data-gallery</code></td>
      <td>
        Groups elements into a gallery by name <code class="text-nowrap">data-gallery="galleryName"</code>, enabling navigation between items and animated thumbnails.
      </td>
    </tr>
  </tbody>
</table>

---

## 🎯 Events

Divclass Lightbox provides lifecycle hooks that allow you to interact with the modal during different stages.


```js
const lightbox = new DivclassLightbox('[data-dc-lightbox]');

lightbox.on("layoutReady", ({ modalRef }) => {
  const heading = modalRef.querySelector("h2");

  if (heading) {
    heading.innerHTML = "New Text";
  }
});
```

## Available Events

| Event               | Description                                    |
| ------------------- | ---------------------------------------------- |
| `beforeLayoutOpen`  | Fired before the modal layout is prepared      |
| `layoutReady`       | Fired when the layout is inserted into the DOM |
| `layoutOpened`      | Fired when the modal becomes visible           |
| `beforeLayoutClose` | Fired before the modal starts closing          |
| `layoutClosed`      | Fired after the modal is fully closed          |

---

## 🌐 Global Methods

### `DivclassLightbox.show(options)`

Open a lightbox programmatically.

### `DivclassLightbox.closeAll()`

Close all currently opened lightboxes.

### `DivclassLightbox.destroyAll()`

Destroy all initialized lightbox instances and remove event listeners.

---

## Why Divclass Lightbox?

Divclass Lightbox focuses on **performance and simplicity**.

Unlike many heavy lightbox libraries, it keeps the DOM minimal using **virtual slides**, supports **touch gestures**, and works with **zero dependencies**.

---

## 🌐 Browser Support

* Chrome
* Firefox
* Edge
* Safari
* Opera

Touch devices fully supported (mobile & tablet).

---

## 📄 License

MIT © Taras Bilinskyi

