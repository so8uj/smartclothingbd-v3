# Smart Clothing Ltd — Hero Section

A responsive, pixel-perfect build of the **Smart Clothing Ltd** hero page, converted from the client's Figma design to plain HTML, CSS and a little JavaScript.

## Design source (Figma)

**[Smart Clothing Ltd — Redesign (Copy) — client Figma file](https://www.figma.com/design/3SymTZ0MpdKvcVENQRmus6/Smart-Clothing-Ltd-%E2%80%94-Redesign--Copy-?node-id=0-1&t=NHO8vPBz3uZskaRq-1)**

The desktop layout (1440px frame) follows the Figma values exactly: positions, font sizes, line heights and spacing are taken straight from the frame. The design has tight, uneven spacing in places, so open the Figma file next to the page to compare. The tablet and phone layouts are responsive adaptations of that frame.

## Features

- Pixel-accurate desktop layout from the Figma frame (1440px)
- Responsive down to small phones (breakpoints: 1360 · 1280 · 1180 · 1100 · 900 · 700 · 600 · 360)
- Header that hides on scroll down and slides back on scroll up
- "Work with us" button with an infinite marquee
- Click-to-play YouTube video loaded in place of the poster image
- Simple fade-in animations on load and scroll (respects reduced-motion settings)
- Hover states on buttons, links, certificates and feature icons

## Project structure

```
index.html   page markup + small inline scripts (menu, header scroll, video, reveal)
style.css    all styles, organised in 6 sections (see below)
img/         images and icons exported from Figma
```

## CSS structure

`style.css` is organised so each class lives in one block, with its responsive overrides and hover states nested inside it.

1. **Design tokens** (`:root`): colours, fonts, weights, font sizes, spacing, radius, motion and z-index. Change these to re-theme the site.
2. **Base**: reset, body, links, focus ring
3. **Layout**: `.page`
4. **Components**: `.btn`, `.header`, `.hero`, `.video`, `.certs`, `.features`
5. **Utilities**: reusable helpers such as `.uppercase`, `.capitalize`, `.fw-*`, `.fs-*`, `.text-primary`, `.text-muted`, `.nowrap` and `.gutter`
6. **Motion**: keyframes and the scroll-reveal styles

### Theming

Colours are CSS custom properties, for example `--color-primary`, `--color-bg`, `--color-text` and `--color-text-muted`. To create a new theme, override them, for example:

```css
:root {
  --color-primary: #e34b10;
}
```

## Changing the video

In `index.html`, edit the play button's data attributes:

```html
<button class="play" data-video="XnY3sQsPtPU" data-start="6">
```

`data-video` is the YouTube video ID and `data-start` is the start time in seconds. The page needs to be served over http(s), not opened as a plain file, for YouTube to play.

## Running locally

No build step. Open `index.html` in a modern browser, or serve the folder with any static server.

The stylesheet uses native CSS nesting and `text-box: trim`, so it needs a current version of Chrome, Edge, Safari or Firefox.
