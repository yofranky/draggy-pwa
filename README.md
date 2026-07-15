# Draggy — Gobble, Giggle, Grow! 🐉

Draggy is a high-performance dragon arena game developed as an installable Progressive Web App (PWA). This project represents a collaboration between myself and AI development partners to create a seamless, ad-free gaming experience.

**[Play It Live](https://yofranky.github.io/draggy-pwa/)**

---

## The Experience

Players guide a hatchling dragon through a shared arena, consuming glowing essence orbs to increase in size while outmaneuvering six AI-controlled rivals. In this arena-survival format, colliding with another dragon means elimination, but defeating a rival allows you to collect their remaining length as a high-value bounty.

* **Controls:** The game supports both drag-anywhere mechanics and fixed on-screen joysticks, with full keyboard support for desktop users.
* **Accessible Design:** The game utilizes an Okabe-Ito colorblind-safe palette. To ensure clarity, each dragon is distinguished by unique crest and horn silhouettes rather than color alone.
* **Customization:** Features include toggleable haptics, sound effects, a reduce-motion mode, and real-time arena ranking.

## The Development Process

This game was built using an AI-assisted development workflow. My role as the Technical Program Manager and lead developer involved defining the core architecture, testing for performance, and ensuring the final product met the BKAOS standard for quality and accessibility.

My primary motivation for this project was to learn the PWA ecosystem through hands-on development. By involving my children as my testing team, I established a high-energy feedback loop that prioritized real-world usability. This approach ensured the game remained intuitive, fun, and friction-free.

## Why a PWA?

While the project began with the goal of an App Store release, I chose to launch as a PWA to prioritize immediate access for my family. This model offers several advantages:

* **Zero-Friction Access:** Users can launch the game directly via a URL. There are no app store accounts to create, no passwords to remember, and no download queues.
* **Rapid Updates:** Hosting as a PWA allows me to deploy bug fixes and new features instantly, rather than waiting for external approval processes.
* **Privacy and Performance:** The game contains no trackers, ad SDKs, or heavy frameworks. It is built with vanilla HTML, CSS, and JavaScript, ensuring a fast, lightweight experience that works offline.

## Technical Implementation

This project is built using native browser technologies, including the Canvas API for rendering, the Web Audio API for sound, and the Vibration API for haptics.

To maintain performance, I implemented object pooling for essence orbs, which eliminates the lag typically caused by constant memory allocation. Additionally, I developed an arc-length resampling algorithm for the dragon’s tail to ensure fluid, consistent movement even during high-speed boosts or sharp turns.

## Deployment and Local Use

This project is hosted via GitHub Pages and is fully installable.

1. **Mobile:** Navigate to the game link in your browser, then select "Add to Home Screen" from your browser’s menu.
2. **Desktop:** Select the "Install" icon typically found in your browser’s address bar.

For those interested in the source code, you can run the project locally by executing `npx serve .` in your terminal. Note that a local server is required to trigger the service worker and offline functionality.

---

*Draggy is a BKAOS project.*
