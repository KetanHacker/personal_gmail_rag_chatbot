# Gmail RAG Assistant

A Retrieval Augmented Generation (RAG) system that allows you to ask questions about your Gmail emails using AI. This project fetches emails from your Gmail account, processes them into a vector database, and provides an interactive chat interface to query your email content.

## Features

- 🔐 Secure Gmail API authentication
- 📧 Automatic email fetching and processing
- 🔍 Vector-based email search and retrieval
- 💬 Interactive chat interface powered by OpenAI GPT
- 📊 Conversation memory for contextual responses
- 🎨 Modern Gradio web interface

## Prerequisites

- Python 3.8 or higher
- Gmail account with API access enabled
- OpenAI API key

## Setup

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd gmail_rag
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Gmail API Setup

1. Go to the [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. Enable the Gmail API for your project
4. Create credentials (OAuth 2.0 Client ID) for a desktop application
5. Download the credentials file and save it as `credentials.json` in the project root

### 4. OpenAI API Setup

1. Get your OpenAI API key from [OpenAI Platform](https://platform.openai.com/)
2. Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_api_key_here
```

## Usage

### Running the Application

1. Open the Jupyter notebook:
   ```bash
   jupyter notebook project.ipynb
   ```

2. Run all cells in the notebook. The application will:
   - Authenticate with Gmail (browser window will open for first-time setup)
   - Fetch and process your emails
   - Build a vector database
   - Launch the chat interface

3. Access the web interface at the provided URL (typically `http://localhost:7860`)

### Example Queries

- "What emails do I have about travel?"
- "Do I have any security alerts?"
- "What did the last email from Google say?"
- "Summarize my recent emails"

## Configuration

You can modify these settings in the notebook:

- `MODEL`: OpenAI model to use (default: "gpt-4o-mini")
- `MAX_EMAILS`: Maximum number of emails to fetch (default: 100)
- `DB_NAME`: Vector database directory name

## Project Structure

```
gmail_rag/
├── project.ipynb          # Main Jupyter notebook
├── requirements.txt       # Python dependencies
├── .env                  # Environment variables (create this)
├── credentials.json      # Gmail API credentials (create this)
├── token.json           # Gmail auth token (auto-generated)
├── vector_db_emails/    # Vector database (auto-generated)
├── knowledge-base/      # Processed emails (auto-generated)
└── README.md           # This file
```

## Security Notes

- Never commit `credentials.json`, `token.json`, or `.env` files to version control
- The `.gitignore` file is configured to exclude sensitive files
- Your emails are processed locally and stored in a local vector database

## Troubleshooting

### Gmail Authentication Issues
- Ensure Gmail API is enabled in Google Cloud Console
- Check that `credentials.json` is properly downloaded and placed in the project root
- Make sure you're using the correct Google account

### OpenAI API Issues
- Verify your API key is correct and has sufficient credits
- Check that the `.env` file is properly formatted

### Dependencies Issues
- Try updating pip: `pip install --upgrade pip`
- Create a virtual environment if you encounter conflicts

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Disclaimer

This application accesses your Gmail data. Please review the code and ensure you're comfortable with how your data is processed. The application only reads emails and does not send or modify any emails.
