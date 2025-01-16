# AI Video Summarizer 🎥

A powerful video analysis tool that leverages Google's Gemini AI to provide intelligent summaries and insights from video content. Built with Streamlit and Phidata, this application offers an intuitive interface for video analysis and summarization.

## 🌟 Features

- Video upload and processing
- AI-powered content analysis using Gemini 2.0 Flash
- Context-aware responses using DuckDuckGo integration
- Real-time processing status updates
- Markdown-formatted results
- Temporary file handling for security
- Streamlit-based user interface

## 📋 Prerequisites

- Python 3.8+
- Google API Key (Gemini API access)
- Docker (optional, for containerized deployment)

## 🚀 Quick Start

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd ai-video-summarizer
   ```

2. **Set up environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: .\venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Configure environment variables**
   ```bash
   # Create .env file
   cp .env.example .env
   
   # Add your Google API key to .env
   GOOGLE_API_KEY=your_api_key_here
   ```

4. **Run the application**
   ```bash
   streamlit run app.py
   ```

## 🐳 Docker Deployment

Build and run using Docker:

```bash
# Build the image
docker build -t ai-video-summarizer .

# Run the container
docker run -p 8501:8501 -e GOOGLE_API_KEY=your_api_key_here ai-video-summarizer
```

## 🏗️ Architecture

The application follows a layered architecture:

1. **Frontend Layer (Streamlit)**
   - Handles user interface
   - Manages file uploads
   - Displays results

2. **Processing Layer**
   - Video processing service
   - AI analysis service
   - Caching mechanism

3. **Storage Layer**
   - Temporary file storage
   - Results database (optional)

4. **External Services**
   - Gemini AI API
   - DuckDuckGo API

## 💻 Usage

1. Open the application in your web browser (default: http://localhost:8501)
2. Upload a video file (supported formats: MP4, MOV, AVI)
3. Enter your analysis query
4. Click "Analyze Video" to process
5. View the AI-generated insights

## 📁 Project Structure

```
ai-video-summarizer/
├── app.py              # Main application file
├── Dockerfile          # Docker configuration
├── requirements.txt    # Python dependencies
├── .env               # Environment variables
├── .gitignore
└── README.md
```

## ⚙️ Configuration Options

| Variable | Description | Required |
|----------|-------------|----------|
| GOOGLE_API_KEY | Google API Key for Gemini | Yes |
| PORT | Port for the application (default: 8501) | No |
| DEBUG | Enable debug mode (default: False) | No |

## 🔄 API Endpoints (If Running as Service)

- `POST /process-video`: Submit a video for processing
- `GET /status/<job_id>`: Check processing status
- `GET /result/<job_id>`: Retrieve analysis results

## 🛠️ Development

To contribute to the project:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests (if available)
5. Submit a pull request

## 📈 Performance Considerations

- Video file size limit: 100MB
- Supported video formats: MP4, MOV, AVI
- Processing time varies based on video length
- Concurrent processing limited by API quotas

## 🔒 Security Notes

- Files are processed in temporary storage
- Automatic cleanup after processing
- API keys should be kept secure
- Input validation implemented

## 🤝 Contributing

Contributions are welcome! Please read our [Contributing Guidelines](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## 🙏 Acknowledgments

- Google Gemini AI team
- Streamlit community
- Phidata framework
- DuckDuckGo API

## 📧 Support

For support and questions, please [open an issue](issues/new) or contact the maintainers.