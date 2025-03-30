# IITDM-Hacakathon

# Multilingual AI Agent for Personalized, Context-Driven Customer Support

## Problem Statement
Most customer service chatbots in the market today struggle with delivering multilingual, personalized, and context-aware support. Businesses operating globally face challenges in providing seamless customer service across different languages and cultural contexts. Additionally, existing chatbots often fail to retain customer history, leading to frustrating, repetitive interactions.

Our AI-powered customer experience (CX) agent solves these issues by:
- ✅ Offering real-time multilingual support, ensuring seamless communication in multiple languages
- ✅ Providing personalized responses by understanding past interactions and user preferences
- ✅ Delivering context-driven assistance, ensuring relevant and meaningful conversations

With this AI agent, businesses can significantly enhance customer satisfaction, reduce resolution time, and offer a human-like support experience across diverse regions.

## Demo Video
[Link to Demo Video](https://www.youtube.com/watch?v=Nw9EjATS-DU) <!-- Replace with your actual demo video link -->
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/Nw9EjATS-DU/0.jpg)](https://www.youtube.com/watch?v=Nw9EjATS-DU)


## Demo 
<img width="1000" alt="image" src="https://github.com/user-attachments/assets/58b82cda-a9d5-49d7-8231-1adb55e15b9e" />
<img width="981" alt="image" src="https://github.com/user-attachments/assets/c2b07c00-9411-4e15-b2e7-11271b14c508" />
<img width="974" alt="image" src="https://github.com/user-attachments/assets/cb6cee87-fc1f-4830-80ba-894056ac6d6b" />


## Solution Overview
This project implements a WhatsApp-based customer support agent for Noise (an electronics company) with the following key features:

1. **Multilingual Support**: 
   - Supports Hindi, Telugu, Tamil, and Malayalam
   - Automatically detects input language and responds in the same language
   - Translates user queries to English for processing and translates responses back

2. **Context-Aware Responses**:
   - Uses RAG (Retrieval Augmented Generation) to provide accurate information
   - Retrieves relevant content from Noise's support website
   - Maintains conversation history for context-aware responses

3. **Voice Message Support**:
   - Transcribes audio messages using Whisper AI
   - Processes voice queries with the same capabilities as text

4. **Personalized Experience**:
   - Maintains session data for each user
   - Remembers previous interactions for more natural conversations

## Architecture
- **Frontend**: WhatsApp interface using Twilio API
- **Backend**: Flask application with the following components:
  - Language detection and translation services
  - Document retrieval from vectorized knowledge base
  - LLM-powered conversational chain (Groq LLama 3.3 70B model)
  - Audio transcription using OpenAI's Whisper
  - Session management for conversation history

## Technologies Used

### APIs and Models
- **Groq API**: Used for LLM capabilities (LLama 3.3 70B model)
- **Twilio API**: WhatsApp integration
- **Google Generative AI**: Alternative LLM option
- **OpenAI Whisper**: Audio transcription

### Libraries
- **LangChain**: For RAG implementation and conversational chains
- **Flask**: Web framework for the backend
- **Flask-Session**: For session management
- **Chroma DB**: Vector database for document storage
- **SentenceTransformer**: Embedding generation
- **langdetect**: Language detection
- **indic_transliteration**: For handling Indian languages
- **translate**: Text translation
- **BERT-Score**: For evaluation (optional usage)

## Setup and Installation

### Prerequisites
- Python 3.8+
- API keys for Twilio, Groq, and Google Generative AI

### Installation
1. Clone the repository:
```bash
git clone https://github.com/pradeepodela/IITDM-Hacakathon
cd IITDM-Hacakathon
```


2. Set up environment variables:
```bash
export GOOGLE_API_KEY='your_google_api_key'
export GROQ_API_KEY='your_groq_api_key'
export FLASK_SECRET_KEY='your_secret_key'
export TWILIO_ACCOUNT_SID='your_twilio_account_sid'
export TWILIO_AUTH_TOKEN='your_twilio_auth_token'
export TWILIO_PHONE_NUMBER='whatsapp:+1234567890'
```

### Running the Application
```bash
python app.py
```

The application will start running on http://0.0.0.0:5000/

## API Endpoints
- **/** - Health check endpoint
- **/chat** - Main endpoint for processing WhatsApp messages

## Deployment
For production deployment, consider:
- Using a WSGI server like Gunicorn
- Setting up a reverse proxy with Nginx
- Implementing proper security measures for API keys
- Setting up monitoring and logging

## Future Improvements
- Add support for more languages
- Implement more sophisticated translation techniques
- Enhance the RAG system with better retrieval mechanisms
- Add analytics for conversation quality monitoring
- Implement feedback loop for continuous improvement

