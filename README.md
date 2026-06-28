# 🎨 AirDrawer

AirDrawer is a browser-based air-drawing app that turns your webcam and your hand into a neon paintbrush — no mouse, no stylus, no touchscreen. Just point your finger in the air and draw glowing neon trails in real time, powered entirely by computer vision running in your browser.

It uses Google's MediaPipe Hands model to track 21 landmarks on your hand, interprets specific finger gestures as drawing commands, and renders smooth, glowing neon lines onto an HTML canvas overlaid on your webcam feed.

🔗 Try it live: https://areejzahra92.github.io/AirDrawer/

---

## ✋ How It Works

Your hand is tracked frame-by-frame and translated into different modes based on simple finger gestures:

| Gesture | Mode | Action |
|---|---|---|
| ☝️ Index finger only | Draw | Draws a smooth glowing neon line following your fingertip |
| ✌️ Index + Middle finger (victory sign) | Spray | Draws a dual parallel neon stream with a speckled spray-paint effect |
| ✊ Closed fist | Pause | Stops drawing — move your hand without leaving a trail |
| 🖐️ Open palm | Clear | Instantly wipes the canvas clean |

A live status badge in the toolbar always shows which mode is currently active, and a smoothing filter (exponential moving average) is applied to fingertip coordinates so lines come out fluid instead of jittery.

---

## ✨ Features

### 🖼️ Save Snapshot
Click Save to download your current artwork as a .png image — it composites your neon drawing together with the (mirrored) webcam background exactly as you see it on screen, so you can keep or share your creations.

### 🌈 Rainbow Mode
Toggle Rainbow Mode on to make your brush color automatically cycle through the entire hue spectrum (0°–360°) as you draw, instead of using a single fixed color — perfect for vibrant, ever-shifting neon trails.

### 🌙 Background Glow Intensity
A dedicated slider controls the opacity of the webcam feed behind your drawing — turn it down to near 0 for a pitch-black dark room neon aesthetic, or raise it up to clearly see yourself while you draw.

### ↩️ Undo / Redo
Every stroke and every screen-clear is tracked in a history stack. Made a mistake? Hit Undo (or Ctrl+Z) to step back one action at a time, and Redo (Ctrl+Y / Ctrl+Shift+Z) to bring it back — no need to wipe the whole canvas over a small slip.

### 🎨 Multi-Finger Tool Selection
Different finger combinations map to different tools:
- Index finger → standard precision neon line
- Index + Middle finger (✌️) → spray-paint mode: a dual-line parallel stream with scattered speckle particles for a looser, textured effect

### 🎛️ Customizable Brush
- Color picker — choose any solid color for your neon line (disabled automatically while Rainbow Mode is active)
- Size slider — adjust brush thickness from fine detail lines to bold strokes

---

## 🛠️ Tech Stack

- HTML5 Canvas — for rendering the neon glow effects (layered outer bloom + inner white-hot core)
- MediaPipe Hands (https://developers.google.com/mediapipe) — real-time hand landmark detection, fully client-side
- Vanilla JavaScript — no frameworks, no build step
- CSS — UI styling, including a custom gradient toggle switch for Rainbow Mode

No installation, no backend, no dependencies to install — it's a single self-contained HTML file that runs entirely in the browser.

---

## 🚀 Running Locally

1. Clone this repo:
   git clone https://github.com/AreejZahra92/AirDrawer.git
2. Open index.html in a modern browser (Chrome recommended for best webcam/MediaPipe support)
3. Allow camera access when prompted
4. Start drawing in the air! ✋

Or just use the live hosted version: https://areejzahra92.github.io/AirDrawer/

---

## 📋 Controls Summary

| Control | Action |
|---|---|
| Color picker | Set a fixed brush color |
| Rainbow toggle | Enable/disable auto-cycling hue |
| Size slider | Adjust brush/line thickness |
| BG Glow slider | Adjust webcam background visibility |
| Undo button / Ctrl+Z | Revert last stroke or clear |
| Redo button / Ctrl+Y | Reapply an undone action |
| Save button | Download artwork as PNG |

---

## 📄 License

Feel free to use, modify, and build on this project.
