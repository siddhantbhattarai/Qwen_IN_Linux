# How to Use Qwen2.5-VL Locally

## Introduction
Qwen2.5-VL is the flagship vision-language model developed by Qwen. It represents a significant leap forward from its predecessor, Qwen2-VL, by mastering tasks such as recognizing objects, analyzing complex layouts, comprehending lengthy videos, and providing structured outputs for documents.

In this guide, we'll explore how to set up and use Qwen2.5-VL locally on a laptop with 8GB VRAM and also learn how to run it with Docker Desktop.

## Prerequisites
To run Qwen2.5-VL locally, ensure you have the following:

- A laptop with a GPU (8GB VRAM minimum)
- Ubuntu 24.04 (or compatible Linux distribution)
- Python 3.8 or higher installed
- Git installed
- At least 20GB of free disk space

## Table of Contents
- [Introduction](#introduction)
- [Using Qwen2.5-VL Locally](#using-qwen25-vl-locally)
  - [Running the Web Application](#running-the-web-application)
  - [Experimental Streaming Video Chat](#experimental-streaming-video-chat)
  - [Running with Docker Desktop](#running-with-docker-desktop)
- [Using Qwen2.5-VL Online Chatbot](#using-qwen25-vl-online-chatbot)
- [Conclusion](#conclusion)

---

## Using Qwen2.5-VL Locally

### 1. Running the Web Application

1. **Clone the GitHub Repository:**
   ```bash
   git clone https://github.com/QwenLM/Qwen2.5-VL
   cd Qwen2.5-VL
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements_web_demo.txt
   ```

3. **Install PyTorch with CUDA Support:**
   ```bash
   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124
   ```

4. **Update Gradio and Gradio Client:**
   ```bash
   pip install -U gradio gradio_client
   ```

5. **Run the Web Demo Application:**
   ```bash
   python web_demo_mm.py --checkpoint-path "Qwen/Qwen2.5-VL-3B-Instruct"
   ```
   - The application will download the model and start running at http://127.0.0.1:7860.

6. **Interact with the Web Application:**
   - Upload an image and ask questions.
   - Use text-based interactions without an image for LLM capabilities.

### 2. Experimental Streaming Video Chat

To run the streaming video chat demo:

1. **Navigate to the Streaming Demo Directory:**
   ```bash
   cd web_demo_streaming/
   ```

2. **Run the Application:**
   ```bash
   python app.py --checkpoint-path "Qwen/Qwen2.5-VL-3B-Instruct"
   ```

   Grant access to your webcam to interact with the model via streaming video.

### 3. Running with Docker Desktop

The most stable way to use Qwen2.5-VL locally is with Docker.

1. **Install Docker Desktop:**
   Download it from the official [Docker website](https://www.docker.com/products/docker-desktop/).

2. **Run the Docker Container:**
   ```bash
   docker run --gpus all --ipc=host --network=host --rm --name qwen2 -it qwenllm/qwenvl:2-cu121 bash
   ```

This pre-configured Docker image simplifies deployment and ensures compatibility with your system.

---

## Using Qwen2.5-VL Online Chatbot

If you want to experience the flagship model Qwen2.5-VL 72B Instruct online:

1. Visit the [Qwen Chat](https://www.qwenchat.com) website.
2. Create an account and start interacting with the model.
3. Select the appropriate model before uploading images or asking questions.

The online chatbot offers fast and accurate responses, providing a seamless experience.

---

## Conclusion
Qwen2.5-VL demonstrates exceptional accuracy and versatility, redefining the capabilities of vision-language models. This guide has covered how to set up and use the model locally, run experimental demos, and interact online. With its ability to integrate into various workflows, Qwen2.5-VL is a game-changer in the AI landscape.

Explore more about Qwen's models and capabilities by visiting their official GitHub repository.

