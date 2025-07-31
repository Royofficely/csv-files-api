# 📁 CSV File API

A fast, secure, and developer-friendly API for uploading, downloading, and managing large CSV files. Built with FastAPI and JWT authentication, optimized for performance and ease of integration.

## ✨ Features

- 🔒 **JWT Authentication** – Secure access with token-based auth
- 📊 **CSV Validation** – Auto-validates file structure and format
- 💾 **Large File Support** – Handles files >9MB via streaming
- 🚀 **Efficient Upload/Download** – Streamed I/O with minimal memory footprint
- 🔄 **RESTful Interface** – Simple endpoints for file management

## 🛠️ Tech Stack

- Python 3.12
- FastAPI
- JWT Authentication
- File System Storage
- Poetry for dependency management

## 🚀 Getting Started

### Prerequisites

- Python 3.12+
- [Poetry](https://python-poetry.org/)

### Installation

```bash
git clone <repository-url>
cd csv-file-api
poetry install
```

### Running the Server

```bash
poetry run fastapi dev app/main.py
```

The API will be available at `http://localhost:8000`

## 🔑 Authentication

Generate an access token using:

```bash
curl -X POST "https://app-cmqjegeb.fly.dev/api/auth/token" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "username=admin&password=admin123"
```

Save the `access_token` for all future requests.

## 📚 API Endpoints

### 📤 Upload CSV

```bash
curl -X POST "https://app-cmqjegeb.fly.dev/api/files/upload" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -F "file=@your_file.csv"
```

### 📥 Download CSV

```bash
curl -X GET "https://app-cmqjegeb.fly.dev/api/files/FILE_ID" \
  -H "Authorization: Bearer YOUR_TOKEN"
```

### 📋 List All Files

```bash
curl -X GET "https://app-cmqjegeb.fly.dev/api/files" \
  -H "Authorization: Bearer YOUR_TOKEN"
```

### 🗑️ Delete File

```bash
curl -X DELETE "https://app-cmqjegeb.fly.dev/api/files/FILE_ID" \
  -H "Authorization: Bearer YOUR_TOKEN"
```

## 📝 File Specifications

- **Format**: CSV only
- **Max Size**: Tested up to 10MB
- **Validation**: Header + row consistency
- **Storage**: Local file system
- **Encoding**: UTF-8

## 🔒 Security

- ✅ JWT Authentication
- ✅ Protected API routes
- ✅ Input sanitization
- ✅ Secure file handling
- ✅ File type validation

## 🌟 Example Response

### Upload Success

```json
{
  "file_id": "21672364-91bf-4ea7-959d-ec5236dda2e2",
  "filename": "example.csv",
  "message": "File uploaded successfully"
}
```

### File List

```json
{
  "files": [
    {
      "file_id": "21672364-91bf-4ea7-959d-ec5236dda2e2",
      "filename": "example.csv",
      "upload_date": "2025-07-31T10:30:00Z",
      "size": "2.5MB"
    }
  ]
}
```

## 🌍 Deployment

The API is deployed and publicly available at:

**📡 Production URL**: https://app-cmqjegeb.fly.dev

### Local Development

```bash
# Start development server
poetry run fastapi dev app/main.py

# API documentation available at:
# http://localhost:8000/docs
```

## 📖 API Documentation

Interactive API documentation is available at:
- **Swagger UI**: https://app-cmqjegeb.fly.dev/docs
- **ReDoc**: https://app-cmqjegeb.fly.dev/redoc

## ⚠️ Important Notes

- All endpoints require a valid Bearer token
- Files are streamed to avoid memory issues
- Only `.csv` uploads are accepted
- Token security is your responsibility
- Files are stored temporarily and may be cleaned up periodically

## 🧪 Testing

```bash
# Run tests
poetry run pytest

# Run with coverage
poetry run pytest --cov=app
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📫 Support

For issues or feature requests, please open an issue on GitHub.

---

**Made with ❤️ by Roy Nativ**
