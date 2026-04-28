# VoxTranslate

**VoxTranslate** is a zero-latency (simulated), web-based application designed to capture live Portuguese conference audio through the browser and translate it into large, high-contrast English captions. It is built with a strict Brutalist aesthetic, prioritizing extreme legibility and accessibility through a pure black-and-white color palette and dynamic variable typography.

Check out a working live demo: https://pedamado.github.io/voxtranslate/

_Designed by Pedro Amado (FBAUP/i2ADS/Ligatures) and developed by Gemini 3 in Antigravity. (April, 2026)._

## Features

- **Real-Time Speech-to-Text:** Utilizes the browser's native Web Speech API (`webkitSpeechRecognition`) to instantly transcribe spoken Portuguese (`pt-PT`).
- **Free Contextual Translation:** Integrates a free Google Translate endpoint for rapid English translations. Employs a custom sliding-window context buffer to help the API resolve pronouns and contextual grammar without requiring costly LLM API keys.
- **Dynamic VU Meter:** Features a responsive microphone amplitude visualizer powered by `p5.js` and `p5.sound.js`.
- **Brutalist, High-Contrast UI:**
  - Strictly `#000000` and `#ffffff` color scheme.
  - Automatically respects system `prefers-color-scheme` with a manual Light/Dark toggle override.
  - Inter Variable font implementation allowing live adjustment of Font Size (`0.5em` - `10.0em`) and Font Weight (`100` - `900`).
- **Phrase Limiter:** Automatically forces the translation engine to finalize and translate phrases after 5 seconds of continuous speech, ensuring captions remain concise and easy to read.
- **Persistent Settings:** All customizations (Microphone ID, Gain Boost, UI Theme, Font Size, Font Weight, and PT Visibility) are saved directly to `localStorage` for seamless reloads.

## Technologies Used

- **HTML5 / CSS3 / Vanilla JavaScript** (Zero build-step architecture)
- **Web Speech API** (Speech-to-Text)
- **Google Translate Free API** (Text-to-Text)
- **p5.js & p5.sound.js** (Audio Context and Amplitude Analysis)

## Prerequisites

Due to strict browser security policies regarding microphone access (`getUserMedia`) and the Web Speech API, this application **must** be served over a secure context (`https://` or `http://localhost`). It will not work if you simply double-click the `index.html` file (`file://` protocol).

**Supported Browsers:** Google Chrome or Chromium-based browsers are strongly recommended for full `webkitSpeechRecognition` compatibility.

## How to Run Locally

1. Clone or download this repository.
2. Open a terminal and navigate to the project folder.
3. Start a local development server. If you have Python installed, you can run:

   ```bash
   python3 -m http.server 8000
   ```

   _(Alternatively, use `npx serve` or any other HTTP server of your choice)._

4. Open your browser and navigate to `http://localhost:8000`.
5. Allow microphone permissions when prompted.

## Usage

1. Open the **Settings Drawer** by clicking the settings icon in the top right.
2. Ensure your preferred microphone is selected in the **Microphone Input** dropdown.
3. Click **START MIC** to begin capturing audio.
4. Speak in Portuguese. You can monitor the real-time transcription at the top of the screen (or hide it via the "Show Original PT" toggle), and the English translation will appear as large captions scrolling up from the bottom.
5. Use the sliders to adjust the **Input Gain Boost** (to make the VU meter more responsive), **Font Size**, and **Font Weight** to your exact liking.

## License

This project is intended for educational and accessible communication purposes.
