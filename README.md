# 📁 CSV File API

 A secure and efficient API for handling CSV file uploads and downloads, with support for large files.

 ## ✨ Features

 - 🔒 Secure JWT Authentication
- 📊 CSV File Validation
- 💾 Large File Support (Tested with 9.2MB files)
- 🚀 Efficient Streaming Upload/Download
- 🔄 Easy-to-use REST API

 ## 🛠️ Tech Stack

 - FastAPI
- Python 3.12
- JWT Authentication
- File System Storage

 ## 🚀 Getting Started

 ### Prerequisites

 - Python 3.12+
- Poetry (Package Manager)

 ### Installation

 1. Clone the repository
```bash
git clone <repository-url>
cd csv-file-api
```

 2. Install dependencies
```bash
poetry install
```

 3. Run the server
```bash
poetry run fastapi dev app/main.py
```

 ## 🔑 Authentication

 Get your access token:
```bash
curl -X POST "https://app-cmqjegeb.fly.dev/api/auth/token" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "username=admin&password=admin123"
```

 ## 📚 API Endpoints

 ### 1. 📤 Upload CSV File
```bash
curl -X POST "https://app-cmqjegeb.fly.dev/api/files/upload" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -F "file=@your_file.csv"
```

 ### 2. 📥 Download CSV File
```bash
curl -X GET "https://app-cmqjegeb.fly.dev/api/files/FILE_ID" \
  -H "Authorization: Bearer YOUR_TOKEN"
```

 ### 3. 📋 List All Files
```bash
curl -X GET "https://app-cmqjegeb.fly.dev/api/files" \
  -H "Authorization: Bearer YOUR_TOKEN"
```

 ## 📝 File Specifications

 - File Type: CSV only
- Size: Efficiently handles large files
- Storage: File system-based storage
- Validation: Automatic CSV format validation

 ## 🔒 Security

 - JWT Token Authentication
- Secure File Handling
- Protected Endpoints
- Input Validation

 ## 🌟 Example Response

 ```json
{
  "file_id": "21672364-91bf-4ea7-959d-ec5236dda2e2",
  "filename": "example.csv",
  "message": "File uploaded successfully"
}
```

 ## 🚀 Deployment

 The API is deployed and accessible at:
```
https://app-cmqjegeb.fly.dev
```

 ## ⚠️ Important Notes

 - All endpoints require authentication
- Files are validated for CSV format
- Large files are handled efficiently through streaming
- Keep your authentication token secure

 ## 📫 Support

 For any questions or issues, please open an issue in the repository.
