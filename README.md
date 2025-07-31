📁 CSV File API

A fast, secure, and developer-friendly API for uploading, downloading, and managing large CSV files. Built with FastAPI and JWT auth, optimized for performance and ease of integration.

⸻

✨ Features
	•	🔒 JWT Authentication – Secure access with token-based auth
	•	📊 CSV Validation – Auto-validates file structure and format
	•	💾 Large File Support – Handles files >9MB via streaming
	•	🚀 Efficient Upload/Download – Streamed I/O with minimal memory footprint
	•	🔄 RESTful Interface – Simple endpoints for file management

⸻

🛠️ Tech Stack
	•	Python 3.12
	•	FastAPI
	•	JWT Authentication
	•	File System Storage
	•	Poetry for dependency management

⸻

🚀 Getting Started

Prerequisites
	•	Python 3.12+
	•	Poetry (https://python-poetry.org/)

Installation

git clone <repository-url>
cd csv-file-api
poetry install

Running the Server

poetry run fastapi dev app/main.py


⸻

🔑 Authentication

Generate an access token using:

curl -X POST "https://app-cmqjegeb.fly.dev/api/auth/token" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "username=admin&password=admin123"

Save the access_token for all future requests.

⸻

📚 API Endpoints

📤 Upload CSV

curl -X POST "https://app-cmqjegeb.fly.dev/api/files/upload" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -F "file=@your_file.csv"

📥 Download CSV

curl -X GET "https://app-cmqjegeb.fly.dev/api/files/FILE_ID" \
  -H "Authorization: Bearer YOUR_TOKEN"

📋 List All Files

curl -X GET "https://app-cmqjegeb.fly.dev/api/files" \
  -H "Authorization: Bearer YOUR_TOKEN"


⸻

📝 File Specs
	•	Format: CSV only
	•	Max Size: Tested up to 10MB
	•	Validation: Header + row consistency
	•	Storage: Local file system

⸻

🔒 Security
	•	✅ JWT Authentication
	•	✅ Protected API routes
	•	✅ Input sanitization
	•	✅ Secure file handling

⸻

🌟 Example Response

{
  "file_id": "21672364-91bf-4ea7-959d-ec5236dda2e2",
  "filename": "example.csv",
  "message": "File uploaded successfully"
}


⸻

🌍 Deployment

The API is deployed and publicly available at:

📡 https://app-cmqjegeb.fly.dev

⸻

⚠️ Notes
	•	All endpoints require a valid Bearer token
	•	Files are streamed to avoid memory issues
	•	Only .csv uploads are accepted
	•	Token security is your responsibility

⸻

📫 Support

For issues or feature requests, open an issue on GitHub.

Made with ❤️ by Roy Nativ
