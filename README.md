# Feedback Card

An accessible user feedback widget built completely with semantic HTML and modern CSS selectors—zero JavaScript runtime overhead required.

---

## Overview

Most modern web applications rely on heavy JavaScript packages just to handle simple UI states like hover interactions, rating selections, and screen switching. This project proves you don't need hydration steps, DOM manipulation scripts, or third-party libraries for stateful micro-interactions.

By leveraging native browser mechanisms like radio inputs, labels, and the sibling CSS combinator (`~`), this component handles star hover states, text input styling, and stateful screen transitions directly inside the browser's render pipeline.

## How It Works

1. **Reverse Source Order for Hover Dynamics:** The star rating relies on `flex-direction: row-reverse`. This puts the 5-star element first in DOM order within its container while keeping it on the far right visually. Because it comes first in the DOM, targeting modern sibling elements with `~` allows previous stars to highlight effortlessly when hovering over higher ratings.
2. **State Management via Invisible Inputs:** Screen swapping is handled by a hidden `checkbox` element paired with a visual submit button rendered as a `<label>`. Clicking the label toggles the checkbox state, triggering CSS declarations that switch the active screen from the form view to the thank-you screen.

## Key Features

* **Zero-JS Dependency:** Runs smoothly even if JavaScript is blocked or disabled by the client browser.
* **Pure CSS Screen Transitions:** Multi-step UI transitions powered entirely by checkbox state tracking.
* **Native Hover Effects:** Star highlight feedback implemented via CSS flex reversal and general sibling selectors.
* **Responsive Card Layout:** Mobile-friendly container optimized using system typography and standard viewport units.

## Tech Stack Breakdown

* **HTML5:** Semantic structural layout, radio buttons for input states, SVG icons for scalable star rendering.
* **CSS3:** Flexbox layout engine, `@keyframes` animation sequences, CSS attribute and sibling selectors (`:checked`, `~`).

## Prerequisites & Web-Based Quick Start

You don't need to install Node.js, run `npm install`, or set up a local build chain to work on this repository. Everything can be run or edited straight in the browser.

### Option 1: GitHub Codespaces
1. Press `.` (period) on your keyboard while viewing this repository to launch GitHub's web editor instantly.
2. Alternatively, click the green **Code** button at the top right of this repository, select the **Codespaces** tab, and click **Create codespace on main**.
3. Use a lightweight static preview extension (or right-click `index.html` and preview) to test visual changes live.

### Option 2: Local Static File Setup
1. Clone or download the repository files.
2. Open `index.html` directly in any modern browser (Chrome, Firefox, Safari, Edge).

## Project Structure

```text
feedback-card/
├── .github/
│   └── workflows/
│       └── html-css-lint.yml    # Continuous integration for style & structural validation
├── .gitignore                    # Standard OS/editor file exclusions
├── index.html                    # Component markup and inline SVG icons
├── README.md                     # Project documentation
└── style.css                     # Complete design system, state rules, and keyframes
```

## Roadmap

[ ] Add dynamic dark mode support using CSS light-dark() or prefers-color-scheme.

[ ] Integrate native :has() pseudo-class selectors to refine state targeting without top-level wrapper labels.

[ ] Expand keyboard navigation accessibility (:focus-visible outline enhancements for screen-reader users).
