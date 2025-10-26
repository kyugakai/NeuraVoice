# 🧠 NeuraVoice

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#license) [![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/) [![GUI](https://img.shields.io/badge/GUI-Tkinter%20%2B%20Pillow-orange)](#technology-stack) [![LLM](https://img.shields.io/badge/LLM-Ollama%20(local)-purple)](#technology-stack)

NeuraVoice is a next‑gen AI desktop voice assistant built with Python. It combines real‑time speech recognition, natural language processing, a modern Tkinter GUI, and local LLM responses via Ollama to deliver fast, private, and reliable conversations and task automation on your computer.

---

## Overview
NeuraVoice acts as your personal intelligent assistant. Speak naturally to open websites, search Wikipedia, play local music, check date/time, control system actions (shutdown/restart/sleep), and chat using a locally hosted LLM (Ollama). It features a scrollable chat UI, status indicators, and one‑click action buttons.

Unique highlights:
- Local, privacy‑first LLM responses via Ollama (e.g., `llama3.2:3b`)
- Always‑on voice listening with clear status cues in a desktop GUI
- Blends command execution with conversational chat in one app

---

## Key Features
- 🎙️ Voice: Real‑time speech recognition with adjustable listen/cooldown durations
- 🔊 TTS: Natural responses with `pyttsx3`
- 🧠 LLM: Local generation through Ollama with safe fallback responses
- 🧩 Tasks: Wikipedia summaries; open YouTube/Google/Facebook/Instagram/Twitter; launch VS Code or any configured app; play music from a folder; report date/time
- 🖥️ GUI: Tkinter + Pillow interface, scrollable history, live status (Listening/Processing/Idle), quick‑action buttons
- 🧩 Context: Lightweight intent normalization (e.g., “what’s the time” → `time`)

---

## Demo
![NeuraVoice GUI](docs/screenshot.png)

If you don’t have a screenshot yet, add one at `docs/screenshot.png` after capturing the app window.

---

## Technology Stack
- Language: Python 3.9+
- GUI: Tkinter, Pillow (PIL)
- Speech: `speech_recognition`
- TTS: `pyttsx3`
- LLM: Ollama (local), default model `llama3.2:3b`
- Utils: `wikipedia`, `webbrowser`, `os`, `datetime`, etc.

---

## Installation
1. Install Python 3.9+ and Git.
2. Clone the repository:
   ```bash
   git clone https://github.com/arpanpramanik2003/NeuraVoice.git
   cd NeuraVoice
   ```
3. (Recommended) Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   # Windows
   .venv\Scripts\activate
   # macOS/Linux
   source .venv/bin/activate
   ```
4. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
5. Install and run Ollama (for local LLM):
   - Install: https://ollama.com
   - Start the server and pull a model:
     ```bash
     ollama serve &
     ollama pull llama3.2:3b
     ```

---

## Usage
1. Start Ollama (if not already running):
   ```bash
   ollama serve
   ```
2. Launch NeuraVoice:
   ```bash
   python main.py
   ```
3. In the GUI:
   - Click “Single Listen” or enable continuous listening
   - Speak a command or ask a question
   - Watch status change (Listening → Processing → Idle) and view responses in the chat window

---

## Supported Commands (Examples)
- Open websites:
  - “Open YouTube”, “Open Google”, “Open Instagram”, “Open Facebook”, “Open Twitter”
- System info:
  - “What’s the time?”, “Tell me today’s date”
- Wikipedia:
  - “Search Wikipedia for Alan Turing”
- Music:
  - “Play music” (plays from configured folder)
- Apps:
  - “Open VS Code” (or any configured app)
- System controls:
  - “Shutdown the system”, “Restart”, “Sleep”
- General chat (via Ollama):
  - “Explain quantum computing in simple terms.”

Note: Natural phrasing is supported; commands are normalized internally.

---

## Configuration
- Ollama model: Set default model name (e.g., `llama3.2:3b`) in the config section of the code.
- Music directory: Update the path used for playing music.
- App shortcuts: Add or change mappings (e.g., path to VS Code) in the app launcher logic.
- Listening timings: Tune listen duration and cooldown values.

Add a `config.example.json` if you want environment‑based configuration; document keys like:
```json
{
  "ollama_model": "llama3.2:3b",
  "music_dir": "C:/Users/you/Music",
  "vscode_path": "C:/Users/you/AppData/Local/Programs/Microsoft VS Code/Code.exe"
}
```

---

## Project Structure
```
NeuraVoice/
├─ main.py               # App entry point (GUI + controller)
├─ assistants/           # Intent handling, actions, and LLM client
├─ assets/               # Icons, images
├─ docs/
│  └─ screenshot.png     # Demo UI screenshot
├─ requirements.txt      # Python dependencies
└─ README.md             # This file
```
(Adjust based on your actual files.)

---

## Troubleshooting
- Microphone not detected: Check OS input settings and device permissions.
- No TTS audio: Ensure speakers are set as default output; try a different `pyttsx3` voice/driver.
- Ollama errors or slow replies: Confirm `ollama serve` is running and the model is pulled; try a smaller model.
- Wikipedia timeouts: Retry or check internet connectivity.
- GUI freezes: Avoid long‑running work on the main thread; consider threading for blocking calls.

---

## Contributing
Contributions are welcome! Please:
1. Fork the repo and create a feature branch.
2. Follow a clean commit style and include tests or demo steps where possible.
3. Open a pull request with a clear description and screenshots if UI changes.

---

## Roadmap
- Hot‑word activation (optional wake word)
- Pluggable skills system and command registry
- Multi‑model support (switch Ollama models at runtime)
- Conversation memory with history controls
- Cross‑platform packaging (Windows/macOS/Linux installers)

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file.

## Acknowledgments
- Ollama team for local LLM infrastructure
- Python community and maintainers of `speech_recognition`, `pyttsx3`, `wikipedia`
- Tkinter/Pillow contributors for accessible desktop UI
