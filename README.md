# Voice-Driven Live2D Demo

A browser-based demo that uses your microphone to drive Live2D character animations in real-time. Speak or make sounds, and the character's mouth will move in sync with your voice.

## Features

- **Voice-Driven Lip Sync** - Real-time mouth animation driven by microphone input
- **Multiple Models** - Choose from 5 cute Live2D characters (Shizuku, Haru, Hijiki, Tororo, Koharu)
- **Eye Tracking** - The character's eyes follow your mouse cursor
- **Click Interaction** - Click on the character to trigger random motions
- **Audio Visualization** - Real-time volume meter and expanding ring effects
- **Adjustable Sensitivity** - Fine-tune how responsive the lip sync is to your voice

## Quick Start

Simply open `index.html` in a modern browser:

```bash
# Option 1: Open directly
open index.html

# Option 2: Use a local server (recommended for best compatibility)
python3 -m http.server 8000
# Then visit http://localhost:8000
```

## Usage

1. **Open the page** - The default model (Shizuku) will load automatically
2. **Click the microphone button** at the bottom to enable voice input
3. **Allow microphone access** when the browser prompts you
4. **Start speaking** - The character's mouth will animate in sync with your voice
5. **Move your mouse** - The character's eyes will follow your cursor
6. **Click the character** - Triggers a random animation
7. **Switch models** using the dropdown in the top-right corner
8. **Adjust sensitivity** with the slider to match your microphone level

## Models Included

| Model | Type | Description |
|-------|------|-------------|
| Shizuku | Cubism 2 | Classic anime girl (default) |
| Haru | Cubism 4 | Cheerful greeter |
| Hijiki | Cubism 2 | Cute black cat |
| Tororo | Cubism 2 | Cute white cat |
| Koharu | Cubism 2 | Gentle anime girl |

## Technical Details

- **Rendering**: PixiJS 6.x + pixi-live2d-display
- **Audio**: Web Audio API with AnalyserNode for real-time frequency analysis
- **Lip Sync**: Intercepts the Live2D motion manager update pipeline to inject mouth parameter values derived from audio RMS volume
- **Eye Tracking**: Uses pixi-live2d-display's built-in `focus()` API

## Browser Requirements

- Modern browser with Web Audio API support (Chrome, Firefox, Edge, Safari)
- Microphone access permission
- No build step required - runs entirely from CDN-hosted dependencies

## License

Live2D models used are provided under the [Live2D Free Material License](https://www.live2d.com/eula/live2d-sample-model-terms_en.html).
