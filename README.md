# Timeline

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge)
![Vanilla JavaScript](https://img.shields.io/badge/Vanilla_JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

A responsive vertical timeline built with HTML5, CSS3, and vanilla JavaScript. It presents chronological events in an alternating layout on larger screens and a single-column layout on mobile, with animated reveals as visitors scroll.

The project is a lightweight starting point for displaying milestones, company history, project progress, or a personal journey. The included demo contains 12 entries spanning 1934 to 2005 with placeholder descriptions.

## Features

- **Responsive layout:** Alternating event panels on desktop, narrower panels on tablet, and a left-aligned timeline on mobile.
- **Scroll-triggered reveals:** Event panels slide and fade into view, while their timeline markers change color.
- **Persistent visibility:** Once revealed, events stay visible as visitors continue scrolling.
- **Customizable appearance:** Colors, spacing, typography, and animation timing are defined in a single stylesheet.
- **Optional marker styles:** CSS variants include diamond, star, and heptagon markers, plus a pulsing animation.
- **Zero external dependencies:** No framework, package installation, backend, or build step is required.

## Technology Stack

| Technology | Role |
| --- | --- |
| HTML5 | Page structure and chronological entries using lists and `<time>` elements. |
| CSS3 | Layout, media queries, gradients, pseudo-elements, transitions, transforms, and optional `clip-path` marker shapes. |
| JavaScript (vanilla) | DOM selection, viewport detection, and reveal behavior through native browser APIs. |

All content is stored directly in the HTML. The application runs entirely in the browser and does not use a database or external API.

## Getting Started

### Prerequisites

A modern web browser with JavaScript enabled. Git is optional if you download the repository as a ZIP archive.

### Run Locally

1. Clone the repository:

   ```bash
   git clone https://github.com/Aishagojo/Timeline.git
   cd Timeline
   ```

2. Open `index.html` in your browser.

No development server or dependency installation is needed. Edit the source files and refresh the browser to see your changes.

## Project Structure

```text
Timeline/
|-- index.html   # Page markup and timeline content
|-- style.css    # Responsive layout, styling, and animations
|-- app.js       # Viewport detection and reveal behavior
`-- README.md    # Project documentation
```

## How It Works

Each event is a list item inside `.timeline`. CSS draws the central line and markers, positions event panels on alternating sides, and initially hides the panels.

On page load, resize, and scroll, JavaScript checks each list item's position using `getBoundingClientRect()`. When the item's bounding rectangle fits fully within the viewport, it receives the `in-view` class. CSS then reveals the panel with a slide-and-fade transition. The class is retained after the item leaves the viewport.

The stylesheet adjusts the layout at two breakpoints:

| Viewport width | Layout |
| --- | --- |
| Above 900px | Alternating panels, each 400px wide. |
| 601px to 900px | Alternating panels, each 250px wide. |
| 600px and below | Left-aligned timeline with panels sized to the viewport. |

## Customization

### Add or Edit Events

Update the list inside `<section class="timeline">` in `index.html`. Add a new event using the existing structure:

```html
<li>
  <div>
    <time datetime="2026">2026</time>
    Describe your milestone here.
  </div>
</li>
```

Keep entries in the order you want them displayed. Their position on the page follows the HTML order; dates are not sorted automatically.

### Update the Appearance

Edit `style.css` to change the page background, intro section, event panels, and timeline markers. Reveal timing is controlled by the transition declarations in the effects section.

### Use Alternative Markers

The default timeline uses circular markers. To use a shape variant, add `timeline-clippy` and one of the following classes to the timeline section:

| Class | Marker shape |
| --- | --- |
| `timeline-rhombus` | Diamond |
| `timeline-star` | Star |
| `timeline-heptagon` | Heptagon |

```html
<section class="timeline timeline-clippy timeline-star">
```

Add `timeline-infinite` to enable the optional pulsing marker animation.

## Deployment

Publish `index.html`, `style.css`, and `app.js` together on a static hosting service, keeping their relative paths intact. No build command or server-side runtime is required.

## Verification

There is no automated test suite configured. After making changes, open the page in a browser and check that events reveal on scroll, remain visible afterward, and display correctly across the desktop, tablet, and mobile breakpoints.

JavaScript is required for the reveal behavior: event panels are hidden by default in CSS. Very tall entries should also be checked on small screens because the reveal logic requires each list item to fit fully within the viewport.

## License

No license file is currently included in this repository.
