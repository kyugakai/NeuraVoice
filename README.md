# 🧠 NeuraVoice – The Next-Gen AI Desktop Assistant

**NeuraVoice** is an advanced AI-powered voice assistant built using **Python**, designed to bring human-like interaction and automation to your desktop environment.  
It seamlessly combines **speech recognition**, **text-to-speech**, **natural language processing**, and **Ollama-based large language model (LLM) integration** — all wrapped in a modern **Tkinter GUI**.

NeuraVoice acts as your **personal intelligent assistant**, capable of understanding your commands, conversing naturally, and performing real-world tasks like opening websites, playing music, fetching information from Wikipedia, and controlling system functions — all through voice.

---

## 🚀 Key Features

### 🎙️ Voice Interaction
- Real-time voice recognition using `speech_recognition`  
- Natural voice responses with `pyttsx3`  
- Wake-word independent continuous listening mode  
- Adjustable listening duration and cooldown time  

### 💬 Intelligent Conversation (Powered by Ollama)
- Integrates with **Ollama LLM API** (`llama3.2:3b` by default)  
- Generates human-like, concise, and context-aware responses  
- Automatic fallback responses when Ollama is unavailable  

### 🧩 Smart Task Execution
- Wikipedia search summaries  
- Opens popular sites: YouTube, Google, Facebook, Instagram, Twitter  
- Plays music from a custom local directory  
- Reports current **time** and **date**  
- System controls: shutdown, restart, sleep  
- Launches Visual Studio Code or any app (configurable)

### 🧠 Context Awareness
- Remembers user identity (e.g., your name, university, and role)  
- Differentiates between system commands and conversational queries  
- Uses natural query normalization to handle casual speech (e.g., “Tell me what time it is” → “time”)

### 🖥️ Modern GUI Interface
- Built using **Tkinter + Pillow (PIL)**  
- Scrollable conversation history window  
- Real-time status updates (listening, processing, idle, etc.)  
- Custom buttons for one-click actions (Single Listen, Music, YouTube, Google, Exit)  
- Dynamic theme with dark background and Microsoft-style buttons  

---

## ⚙️ Tech Stack

| Component | Library / Tool |
|------------|----------------|
| **Programming Language** | Python 3.x |
| **Speech Recognition** | `speech_recognition` |
| **Text-to-Speech (TTS)** | `pyttsx3` |
| **LLM Integration** | `Ollama` (local API) |
| **GUI Framework** | `Tkinter` + `PIL` |
| **Knowledge Source** | `wikipedia` |
| **Networking** | `requests`, `webbrowser` |
| **Threading** | `threading.Thread` for async listening |
| **System Control** | `os` module command |
