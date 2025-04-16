# 🎙️ Funny Audio Rewriter Agent

This is an end-to-end Flask-based application that takes a speech audio file, transcribes it, and generates a funny version of the same sentence by adding dramatic pauses, fumbles, and exaggerated expressions — all while keeping the original wording.

It uses:
- 🎧 [Faster-Whisper](https://github.com/guillaumekln/faster-whisper) for audio transcription
- 🤖 [DeepSeek LLM](https://huggingface.co/deepseek-ai/deepseek-coder-1.3b-base) to add expressive humor
- 🔊 [gTTS](https://pypi.org/project/gTTS/) + [pydub](https://pypi.org/project/pydub/) for text-to-speech

---

## 🛠️ Installation
```bash
pip install faster-whisper flask transformers torch gtts pydub
apt-get install -y ffmpeg  # if not already installed
```

---

## 🚀 How to Run (Locally)
```bash
python app.py
```

Then POST an audio file to:
```
http://localhost:5000/process-audio
```

---

## 🌐 How to Run in Google Colab
1. Install dependencies:
```python
!pip install faster-whisper flask transformers torch gtts pydub pyngrok ffmpeg-python
!apt-get install -y ffmpeg
```
2. Set up Ngrok:
```python
from pyngrok import ngrok
ngrok.kill()
public_url = ngrok.connect(5000)
print(public_url)
```
3. Replace `if __name__ == "__main__"` with:
```python
from threading import Thread
Thread(target=lambda: app.run(port=5000)).start()
```

---

## 📥 Input Format
- Accepts any of the following audio formats: `.wav`, `.mp3`, `.flac`, `.m4a`, `.ogg`
- Make sure the uploaded file has the correct extension.

---

## 📤 Output
- Returns a `.wav` file containing the transformed funny speech.

---

## 💡 Future Improvements
- Replace `gTTS` with Coqui or Bark for expressive TTS
- Add styles (e.g., sarcastic, dramatic, robotic)
- Build a React/Streamlit frontend

---

## 📄 License
MIT

---

## 🤝 Contributing
PRs and ideas are welcome! Let’s make AI humor better together 😄

