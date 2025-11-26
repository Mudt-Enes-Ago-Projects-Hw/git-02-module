# Flask Blog API

A modular Flask REST API application with authentication and blog management functionality. This project demonstrates a clean architecture with separated concerns using blueprints, models, and controllers.

## 📋 Features

- **Authentication System**: User registration and login endpoints
- **Blog Management**: CRUD operations for blog posts
- **SQLite Database**: Lightweight database with SQLAlchemy ORM
- **JWT Authentication**: Secure token-based authentication
- **Docker Support**: Containerized deployment ready
- **Modular Architecture**: Clean separation of concerns with blueprints

## 🏗️ Project Structure

```
git-02-module/
├── app.py                      # Application entry point
├── Dockerfile                  # Docker configuration
├── requirements.txt            # Python dependencies
└── src/
    ├── config/
    │   └── settings.py        # Application configuration
    ├── controllers/
    │   ├── __init__.py
    │   ├── auth_controller.py # Authentication endpoints
    │   └── blog_controller.py # Blog endpoints
    └── models/
        └── db.py              # Database initialization
```

## 🚀 Getting Started

### Prerequisites

- Python 3.11+
- pip
- Docker (optional, for containerized deployment)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd git-02-module
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   
   Create a `.env` file in the root directory:
   ```env
   JWT_SECRET=your-secret-key-here
   PORT=5000
   SQLITE_DB=app.db
   ```

5. **Run the application**
   ```bash
   python app.py
   ```

   The server will start at `http://localhost:5000`

## 🐳 Docker Deployment

### Build the Docker image

```bash
docker build -t flask-blog-api .
```

### Run the container

```bash
docker run -p 5000:5000 \
  -e JWT_SECRET=your-secret-key \
  -e PORT=5000 \
  -e SQLITE_DB=app.db \
  flask-blog-api
```

## 📡 API Endpoints

### Authentication

- **POST** `/auth/register` - Register a new user
- **POST** `/auth/login` - Login and receive JWT token

### Blog Management

- **GET** `/blog/` - Get all blog posts
- **GET** `/blog/<blog_id>` - Get a specific blog post
- **POST** `/blog/` - Create a new blog post

## 🛠️ Technologies Used

- **Flask 3.0.0** - Web framework
- **Flask-SQLAlchemy 3.1.1** - ORM for database operations
- **PyJWT 2.8.0** - JWT token handling
- **python-dotenv 1.0.0** - Environment variable management
- **SQLite** - Database

## 📝 Configuration

The application uses environment variables for configuration. Available options:

| Variable | Description | Default |
|----------|-------------|---------|
| `JWT_SECRET` | Secret key for JWT tokens | Required |
| `PORT` | Port to run the application | 5000 |
| `SQLITE_DB` | SQLite database filename | app.db |

## 🔧 Development

### Project Architecture

The application follows a modular architecture:

- **Controllers**: Handle HTTP requests and responses
- **Models**: Define data structures and database operations
- **Config**: Manage application settings and environment variables

### Adding New Features

1. Create models in `src/models/`
2. Define controllers in `src/controllers/`
3. Register blueprints in `app.py`

## 📄 License

This project is part of a university assignment.

## 👥 Contributing

This is an educational project. Feel free to fork and experiment!

## 🐛 Known Issues

- User and Blog models need to be implemented
- Authentication endpoints are placeholders
- JWT authentication flow needs to be completed

## 📞 Contact

For questions or issues, please open an issue in the repository.
