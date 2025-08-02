---
title: "AEI CoT-Lab: AI-Enhanced Learning Laboratory"
emoji: "🎓"
colorFrom: "blue"
colorTo: "red"
sdk: "gradio"
python_version: "3.13"
sdk_version: "5.13.1"
app_file: "app.py"
models:
  - "deepseek-ai/DeepSeek-R1"
tags:
  - "education"
  - "learning"
  - "ai-tutor"
  - "american-education-institute"
license: "mit"
---

# AEI CoT-Lab: AI-Enhanced Learning Laboratory
**American Education Institute** - Empowering Education Through AI Innovation

## 🎓 Overview
AEI CoT-Lab is an advanced educational interface that enables synchronized learning between students and AI tutors. Built on **Cognitive Load Theory** and **Active Learning** principles, it creates a collaborative learning environment where students can:

- 🧠 **Synchronized Learning**: AI output paced to match student comprehension speed
- ✍️ **Interactive Thinking**: Students can pause and guide the AI's reasoning process
- 📚 **Deep Understanding**: Step-by-step exploration of complex concepts

## 🚀 Deployment Options

### Option 1: Deploy on Hugging Face Spaces (Recommended for Free Hosting)

1. Fork this repository to your GitHub account
2. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
3. Create a new Space:
   - Space name: `AEI-CoT-Lab`
   - Select SDK: **Gradio**
   - Space hardware: **CPU basic** (free tier)
   - Visibility: Public or Private
4. Link your GitHub repository
5. Add secrets in Space Settings:
   - `API_KEY`: Your API key
   - `API_URL`: Your API endpoint (e.g., `https://api.deepseek.com/beta`)
   - `API_MODEL`: Your model name (e.g., `deepseek-reasoner`)

### Option 2: Deploy on Railway or Render

These platforms support Python apps natively:
1. Connect your GitHub repository
2. Set environment variables in the platform dashboard
3. Deploy (automatic detection of Python app)

### Option 3: Local Development

```bash
# Clone repository
git clone https://github.com/reedrich12/AEI-CoT.git
cd AEI-CoT

# Install dependencies
pip install -r requirements.txt

# Set environment variables
export API_KEY=your_api_key_here
export API_URL=https://api.deepseek.com/beta
export API_MODEL=deepseek-reasoner

# Run the application
python app.py
```

## ⚠️ Important: Vercel Deployment Not Supported

Vercel is designed for static sites and serverless functions, not for running Gradio applications. Gradio apps require a persistent Python server, which Vercel doesn't provide. Please use one of the recommended deployment options above.

## 🔧 Configuration

### Required Environment Variables

```env
API_KEY=your_api_key_here
API_URL=https://api.deepseek.com/beta
API_MODEL=deepseek-reasoner
```

### Optional Variables (for dual-language support)

```env
API_KEY_2=your_secondary_api_key
API_URL_2=your_secondary_api_url
API_MODEL_2=your_secondary_model
```

## 📖 Usage Guide

1. **Set Learning Objective**: Enter your educational question or topic
2. **Adjust Thinking Speed**: 
   - 5 tokens/sec: Deep learning pace
   - 10 tokens/sec: Standard following pace
   - 50 tokens/sec: Quick review pace
3. **Interactive Learning**:
   - Click `Generate` to start
   - Use `Shift+Enter` to pause/resume
   - Edit the AI's reasoning when paused
   - Guide the learning process

## 🎨 Features

- **AEI Branding**: Professional educational institution design
- **Bilingual Support**: English and Chinese interfaces
- **Adaptive Pacing**: Adjustable thinking speed
- **Real-time Collaboration**: Edit and guide AI reasoning
- **Educational Focus**: Optimized for learning outcomes


## 📄 License
MIT License © 2024 American Education Institute

## 🤝 Support
For support and questions, please open an issue on GitHub or contact the AEI team.

---

*Note: This application requires a compatible AI API (DeepSeek, OpenAI, etc.) for operation. Vercel deployment is not supported as Gradio requires a persistent Python server.*