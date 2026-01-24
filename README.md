# Premium SaaS Components

This repository contains premium, high-quality UI components including an infinite marquee carousel and a comprehensive footer with parallax reveal effects.

## Project Structure

- `css/styles.css`: Combined stylesheet for all components.
- `samples/`: Example HTML files demonstrating the components.
    - `index.html`: **Infinite Marquee Carousel** demo.
    - `footer.html`: **Premium Footer** demo (FAQ + CTA + Footer).

## Components & Classes

### 1. Infinite Marquee Carousel (`carousel-demo` body class)
To use the carousel, ensure the body has `.carousel-demo` class for centering (optional, if used as standalone).

- `.marquee-wrapper`: Main container. Add `data-autoscroll="true"` to enable auto-scrolling.
- `.marquee-track`: Flex container for cards.
- `.card`: Individual carousel item. Hover effects (push, dim neighbors) are built-in.
    - `.play-icon`: Centered icon with glassmorphism and cyan glow on hover.
    - `.logo-text`: Vertical text badge.

### 2. Premium Footer with Drawer Reveal

The footer uses a "drawer reveal" architecture where the CTA section is sticky and revealed from underneath the content.

**Structure:**
1. **Main Content Wrapper** (`.main-content-wrapper`):
    - Contains your main page content (e.g., FAQ).
    - Must have `position: relative`, `z-index: 2`, `background-color`, and `padding-bottom: 150vh` (to allow for the reveal space).
2. **Footer Reveal Container** (`.footer-reveal-container`):
    - Contains the sticky CTA.
    - `position: relative` (wrapper).
    - The child `.footer-cta` is `sticky`.

**Classes:**
- `.footer-cta`: The sticky element (`bottom: 0`, `z-index: -1`).
    - Has a cyan grid overlay (`background-attachment: fixed`).
- `.faq-section`: Example content section with accordions.
- `.site-footer`: Standard footer at the bottom.

### 3. Animations

- `.animate-on-scroll`: Add this class to any element you want to animate in when scrolled into view.
    - Uses an `IntersectionObserver` in JS (see `samples/footer.html`).
    - Animation: `springUp` (slide up with spring physics).
- `.trust-popup`: Fixed position popup notification.
    - `.hidden`: Triggers the exit animation (slide down and fade out).

## Usage

1. Link `css/styles.css` in your HTML `<head>`.
2. Copy the HTML structure from `samples/` files.
3. Ensure the CSS variables in `:root` match your design system if integrating into an existing project.
