# JS Beat Looper 🟡🥁

A simple, fun, browser-based beat machine and step sequencer built with vanilla JavaScript and the powerful **Tone.js** library. Create and loop beats right in your browser with no installation required.

### [➡️ Click here for the Live Demo](https://yaksh9737.github.io/MusicJs/index.html)
*(You'll need to host this on a service like GitHub Pages to create a live link. Replace the URL above with your own.)*

---

## ✨ Features

-   **16-Step Sequencer:** A pre-programmed 16-step beat and melody sequence that loops seamlessly.
-   **Synthesized Sounds:** All sounds (Kick, Snare, Hat, Melody) are generated in real-time by Tone.js.
-   **Interactive Controls:**
    -   Start and stop the looping beat.
    -   Manually trigger individual drum sounds to test them.
-   **Volume Mixer:** Independent volume controls for Master output, Kick, Snare, Hat, and the Melody line.
-   **Zero Dependencies:** Runs entirely in the browser. There's no build step, no `npm install`. Just open the HTML file.

---

## 🚀 How to Use

This project is designed to be incredibly simple to run.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/yaksh9737/MusicJs.git
    ```

2.  **Navigate to the folder:**
    ```bash
    cd MusicJs
    ```

3.  **Open the file:**
    Simply open the `index.html` file in your favorite web browser (like Chrome, Firefox, or Safari).

4.  **Start the Beat!**
    Click the **▶️ Start Beat** button to begin the loop. Browsers require a user interaction (like a click) to enable audio, so this first click is essential.

---

## 💻 Technology Stack

This project is intentionally kept simple and relies on core web technologies.

-   **HTML5:** For the structure and layout of the user interface.
-   **CSS3:** For styling the dark theme, buttons, and sliders. Flexbox is used for layout.
-   **Vanilla JavaScript (ES Modules):** All the logic for the sequencer and UI controls is written in modern JavaScript, loaded directly in the browser as a module.
-   **[Tone.js](https://tonejs.github.io/):** The heart of the project. A powerful Web Audio framework used for:
    -   Scheduling musical events with sample-accurate timing (`Tone.Transport`).
    -   Synthesizing all the sounds (`MembraneSynth`, `NoiseSynth`, etc.).
    -   Managing audio signal routing and volume (`Tone.Volume`).

---

## 🛠️ Code Breakdown

The entire application is contained within `index.html`.

-   **HTML (`<body>`):** Contains the semantic structure for the title, buttons, and volume sliders. Each interactive element has a unique `id` for easy access from JavaScript.
-   **CSS (`<style>`):** Defines the dark, monospace aesthetic. It uses flexbox to center the content and organize the controls cleanly.
-   **JavaScript (`<script type="module">`):**
    1.  **Import Tone.js:** It imports Tone.js directly from a CDN, which is why no installation is needed.
    2.  **Instrument Setup:** Creates instances of different Tone.js synthesizers (`MembraneSynth` for the kick, `NoiseSynth` for the snare, etc.) and connects them through volume controls to the main destination.
    3.  **Sequencer Data:** The `beat` and `notes` arrays are 2D arrays that define the 16-step pattern for the drums and melody. `null` or `[]` represents a rest.
    4.  **The Loop:** `Tone.Transport.scheduleRepeat()` is the core of the looper. It's a callback function that fires on every 8th note, reads the current step from the arrays, and triggers the corresponding sounds.
    5.  **UI Event Listeners:** Standard `addEventListener` calls link the HTML buttons and sliders to their respective Tone.js functions (`Tone.Transport.start()`, `kick.triggerAttackRelease()`, changing volume levels, etc.).

---

## 💡 Possible Future Improvements

-   **Visual Sequencer:** Create a grid of clickable boxes to allow users to program their own beats.
-   **More Sounds:** Add more synth options or even load samples.
-   **Save/Load Patterns:** Allow users to save their creations to `localStorage` or share them via a URL.
-   **BPM Control:** Add a slider to change the tempo (BPM) of the beat.
-   **Pattern Switching:** Add the ability to create and switch between different beat/melody patterns.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).