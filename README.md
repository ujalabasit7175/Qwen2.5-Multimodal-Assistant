# 🤖 Qwen2.5-VL Multimodal Voice & Webcam Assistant

This repository contains a Google Colab notebook that turns the **Qwen2.5-VL (Vision-Language)** model into a fully interactive, multimodal AI assistant. 

Instead of just typing text prompts, this project integrates **OpenAI's Whisper** and custom **JavaScript webcam controls** so you can literally *talk* to the AI, show it images, feed it videos, and use your live webcam to ask questions about the world in front of you.

## ✨ Key Features

* 🗣️ **Voice-to-Text Integration:** Ask your questions out loud! The notebook uses Whisper to listen to your voice and convert it into text for the AI.
* 📸 **Static Image Analysis:** Upload any image from your computer and ask the AI to describe, analyze, or extract information from it.
* 🎬 **Video Processing:** Pass a video file to the model. It automatically extracts evenly spaced frames so you can ask contextual questions about the video's content.
* 🎥 **Smart Live Webcam Mode:** The absolute coolest feature! It turns on your webcam, detects when you actually start speaking (Voice Activity Detection), snaps a perfectly timed photo, and asks Qwen what it sees. 

## 🚀 Getting Started

Because this project uses a 3-billion parameter model and real-time audio/video processing, it is highly recommended to run this in **Google Colab** with a GPU enabled.

1. Open the notebook in Google Colab.
2. Go to **Runtime > Change runtime type** and select **T4 GPU** (or better).
3. Run the cells sequentially.
4. **Note on Permissions:** When you run the Webcam and Audio cells, your browser will ask for permission to use your camera and microphone. You must click "Allow" for the live features to work.

## 📖 How to Use the Notebook

The notebook is divided into clear, easy-to-use sections:

### 1. Environment Setup & Initialization
Run the first few cells to install the required dependencies (Transformers, Whisper, Decord, etc.) and download the `Qwen/Qwen2.5-VL-3B-Instruct` model into the GPU memory.

### 2. Image Testing
Upload an image when prompted. The script will wait for you to speak your question through your microphone. You can also type extra context if you missed something in your voice prompt!

### 3. Video Testing
Upload a video (e.g., `.mp4`) to your Colab environment and paste the file path into the code. Speak your question, and Qwen will analyze the frames to give you an answer.

### 4. Real-Time Webcam Assistant
Run the final section to launch the live assistant:
* It will ask if you want to **type** or **speak** your questions.
* If you choose to speak, point your camera at an object and ask your question out loud. 
* The script will wait for you to finish speaking, grab the current frame, and give you Qwen's response.
* It runs in a continuous loop! When you are done playing with it, just type or say **"stop"** to safely turn off your webcam.

## 🛠️ Technology Stack
* **LLM / Vision Model:** [Qwen2.5-VL-3B-Instruct](https://huggingface.co/Qwen/Qwen2.5-VL-3B-Instruct)
* **Audio Transcription:** [OpenAI Whisper (Base)](https://github.com/openai/whisper)
* **Frameworks:** PyTorch, Hugging Face Transformers
* **Webcam/Mic Interface:** Custom HTML/JS bridging via IPython for Google Colab

## 🤝 Contributing
Feel free to fork this repository, open issues, or submit PRs if you want to add new features (like TTS so the AI talks back!) or optimize the code.
