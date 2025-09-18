AI CFO Assistant: Financial Document Analysis & Reporting
![alt text](https://img.shields.io/badge/License-MIT-yellow.svg)
The AI CFO Assistant is a powerful web application designed to automate the extraction, analysis, and interpretation of financial data from documents like PDFs and spreadsheets. It leverages advanced data ingestion, machine learning, and AI-powered insights (via Ollama) to provide users with a comprehensive financial dashboard, risk assessment, trend forecasting, and an interactive chat assistant.
✨ Key Features
Multi-Format Document Upload: Ingest financial reports in PDF, Excel (.xlsx, .xls), and CSV formats.
Advanced Data Ingestion: Intelligently extracts text, tables, and even data from images (via OCR) within PDFs.
Automated Financial Metrics Calculation: Automatically identifies and calculates key metrics like Revenue, Profit, Assets, Liabilities, and derived KPIs (e.g., Profitability, Debt-to-Equity, Cash Runway).
Comprehensive Health Analysis: Generates an overall financial health score and provides a detailed breakdown of risks and opportunities with actionable recommendations.
AI-Powered Trend Forecasting: Utilizes Prophet or Scikit-learn to predict future trends for Revenue, Profit, and Cash Flow across conservative, realistic, and optimistic scenarios.
Interactive AI Chat: A conversational AI assistant (powered by a local Ollama model) that can answer questions about the financial reports in natural language.
Dynamic & Interactive Dashboard: Visualizes complex financial data through a rich set of charts and graphs using Plotly.
Multi-Report Comparison: Automatically detects reports from the same company for different financial years and generates year-over-year comparison analyses.
One-Click Report Export: Generate and download professional, detailed reports in PDF or Excel formats.
Secure User Management: Features a complete user authentication system (Sign Up, Login, Logout) to keep financial data private.
💻 Technology Stack
Backend: Flask, Python
Frontend: HTML, CSS, JavaScript (with Fetch API for AJAX)
AI & Machine Learning:
LLM Engine: Ollama (for local, private AI chat and report generation)
Forecasting: Prophet, Scikit-learn
NLP/Text Analysis: TextBlob, Levenshtein
Data Processing: Pandas, NumPy
File Ingestion: PyMuPDF (fitz), pdfplumber, openpyxl
OCR: Tesseract (via pytesseract)
Database: SQLite (via Flask-SQLAlchemy)
Visualization: Plotly
Reporting: ReportLab (for PDFs), Openpyxl (for Excel)
🚀 Setup and Installation
Follow these steps to get the application running locally.
1. Prerequisites
Ensure you have the following installed on your system:
Python 3.8+ and pip
Git for cloning the repository.
Ollama: The AI engine. Download and install it from ollama.com.
Tesseract OCR: Required for extracting text from images in PDFs. Follow the installation guide for your OS at tesseract-ocr.github.io.
2. Clone the Repository
code
Bash
git clone https://github.com/your-username/ai-cfo-assistant.git
cd ai-cfo-assistant
3. Set Up a Python Virtual Environment
It's highly recommended to use a virtual environment.
code
Bash
# Create the virtual environment
python -m venv venv

# Activate it
# On Windows:
.\venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
4. Install Dependencies
Install all the required Python packages from the requirements.txt file.
code
Bash
pip install -r requirements.txt
5. Download the Ollama LLM Model
After installing Ollama, make sure its service is running. Then, open your terminal and pull the language model required by the application. This will download several gigabytes.
code
Bash
ollama run llama2:7b-chat
6. Configure Environment Variables
Create a file named .env in the root directory of the project. Copy the contents of .env.example (if provided) or use the template below.
code
Dotenv
# .env file

# A secret key for Flask sessions. Generate a random one for production.
FLASK_SECRET='a_very_secret_and_random_key_for_your_app'

# The base URL for your running Ollama instance (default is usually correct).
OLLAMA_API_BASE_URL="http://localhost:11434"

# The name of the Ollama model to use. Must match the one you downloaded.
OLLAMA_MODEL="llama2:7b-chat"
7. Run the Application
Once the setup is complete, run the Flask application.
code
Bash
python app.py
The application will be available at http://127.0.0.1:5000 in your web browser.
📖 How to Use
Sign Up / Login: Create a new user account or log in with existing credentials.
Upload Documents: On the dashboard, click the "Upload Files" button and select one or more financial reports (PDF, XLSX, CSV).
Analyze Data: The system will process the files in the background. Once complete, a new report card will appear in the "Uploaded Reports" list.
View Dashboard: Click on a report to view the full analysis, including:
Dashboard: An overview with key metrics and visualizations.
Analytics: Detailed charts on KPI performance, forecasts, and risk distribution.
Report: A text-based executive summary generated by the AI.
Chat: An interactive chat window to ask questions about the report.
Compare Reports: If you upload multiple reports from the same company (e.g., for 2022 and 2023), a "Compare" button will appear, enabling year-over-year analysis.
Export Results: Use the "Export" button to download the complete analysis as a formatted PDF or a multi-sheet Excel file.
🔧 Configuration
The application's behavior can be modified via the .env file:
OLLAMA_MODEL: You can switch to a different model (e.g., mistral, llama3) by changing this variable. Make sure you have downloaded the new model first using ollama run <model_name>.
OLLAMA_API_BASE_URL: If you are running Ollama on a different machine or port, update this URL accordingly.
🤝 Contributing
Contributions are welcome! If you'd like to improve the AI CFO Assistant, please follow these steps:
Fork the repository.
Create a new branch for your feature (git checkout -b feature/amazing-feature).
Commit your changes (git commit -m 'Add some amazing feature').
Push to the branch (git push origin feature/amazing-feature).
Open a Pull Request.
