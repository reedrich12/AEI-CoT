# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Common Development Commands

### Running the Application
```bash
# Install dependencies
pip install -r requirements.txt

# Configure environment variables
export API_KEY=your_api_key_here
export API_URL=https://api.deepseek.com/beta  # or your API endpoint
export API_MODEL=deepseek-reasoner  # or your model name

# Optional: Configure secondary API for Chinese language (if using dual-language support)
export API_KEY_2=your_secondary_api_key
export API_URL_2=your_secondary_api_url
export API_MODEL_2=your_secondary_model

# Launch the application
python app.py
```

### Development Workflow
```bash
# The app runs on Gradio by default
# Access at http://localhost:7860 after launching

# For debugging, run directly
python app.py

# To use environment file instead of exports
# Create a .env file with the required variables
```

## High-Level Architecture

### Overview
CoT-Lab is a Human-AI Co-Thinking Laboratory built with Gradio that enables synchronized cognitive collaboration between humans and AI reasoning models. The system allows users to pause, edit, and continue AI's chain of thought reasoning in real-time.

### Core Components

1. **app.py** - Main application file containing:
   - `DynamicState`: Manages UI state and streaming control
   - `ConvoState`: Tracks conversation rounds and API interactions
   - `CoordinationManager`: Controls human-AI synchronization cadence
   - Gradio interface with real-time streaming support

2. **lang.py** - Multi-language configuration supporting English and Chinese interfaces

3. **styles.css** - Custom styling for the Gradio interface

### Key Features & Architecture Patterns

1. **Streaming Chain of Thought**:
   - Uses OpenAI SDK for streaming responses
   - Supports models with separate reasoning content (via `reasoning_content` field)
   - Real-time throughput control (tokens/second) for cognitive synchronization

2. **Human-AI Interaction Model**:
   - Pause/resume functionality during AI reasoning
   - Editable thought process with `Shift+Enter` hotkey
   - Automatic pausing based on paragraph count thresholds

3. **Dual API Support**:
   - Primary API configuration via `API_KEY`, `API_URL`, `API_MODEL`
   - Optional secondary API for Chinese language (suffixed with `_2`)
   - Automatic API switching based on selected language

4. **State Management**:
   - Browser-based persistence using `gr.BrowserState`
   - Real-time UI updates through Gradio's reactive components
   - Conversation history tracking with role-based messages

### Technical Implementation Details

- **Concurrency**: High concurrency limit (1000) for smooth streaming
- **Error Handling**: Graceful degradation with timeout management and error display
- **Thought Editing**: Toggle between editing Chain of Thought only vs full response
- **API Compatibility**: Works with any OpenAI SDK-compatible endpoint