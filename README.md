# Dockerized API Deployment

A professional FastAPI application showcasing modern DevOps practices including containerization, database integration, and production-ready deployment configurations.

## 🚀 Project Overview

This project demonstrates a complete development environment setup for a RESTful API application using FastAPI and PostgreSQL. It serves as a comprehensive example of modern software deployment practices, containerization, and cloud infrastructure management.

### Key Features

- **🐍 FastAPI Application**: Modern, fast web framework for building APIs with Python
- **🐘 PostgreSQL Database**: Robust relational database with proper schema design
- **🐳 Docker Containerization**: Complete containerization with Docker and Docker Compose
- **🔧 Production-Ready**: Configured for deployment on cloud infrastructure
- **📊 Database Management**: CRUD operations for users, movies, and reviews
- **🔐 Error Handling**: Comprehensive exception handling and logging

## 🏗️ Architecture

The application follows a clean architecture pattern with clear separation of concerns:

```
├── api/
│   ├── main.py          # FastAPI application entry point
│   ├── db.py            # Database operations and queries
│   ├── schemas.py       # Pydantic models for data validation
│   ├── exceptions.py    # Custom exception classes
│   ├── setup.py         # Database connection and table creation
│   └── requirements.txt # Python dependencies
├── docker-compose.yml   # Multi-container orchestration
├── Dockerfile          # Container image configuration
└── README.md           # Project documentation
```

## 🛠️ Technology Stack

- **Backend**: FastAPI (Python 3.10)
- **Database**: PostgreSQL 13
- **Containerization**: Docker & Docker Compose
- **ORM**: Raw SQL with psycopg2
- **Data Validation**: Pydantic
- **Logging**: Python logging with file and console handlers

## 📋 API Endpoints

### Core Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/status` | Health check endpoint |
| GET | `/movies` | List all movies |
| GET | `/movie/{movie_id}` | Get specific movie details |
| GET | `/users` | List all users |
| POST | `/users` | Create a new user |
| PUT | `/user/{user_id}` | Update user information |
| DELETE | `/user/{user_id}` | Delete a user |
| POST | `/reviews` | Create a movie review |

### Data Models

- **Users**: User management with unique usernames
- **Movies**: Movie catalog with genre relationships
- **Reviews**: User reviews with ratings and text
- **Genres**: Movie categorization system

## 🚀 Quick Start

### Prerequisites

- Docker and Docker Compose installed
- Git for version control

### Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/Dockerized-API-Deployment.git
   cd Dockerized-API-Deployment
   ```

2. **Start the application**
   ```bash
   docker-compose up --build
   ```

3. **Access the API**
   - API: http://localhost:8000
   - Interactive API docs: http://localhost:8000/docs
   - Alternative docs: http://localhost:8000/redoc

### Environment Variables

The application uses the following environment variables (configured in docker-compose.yml):

- `DATABASE`: PostgreSQL database name
- `PASSWORD`: Database password
- `DB_HOST`: Database host (defaults to localhost)
- `DB_PORT`: Database port (defaults to 5432)

## 🏭 Production Deployment

This project is designed for cloud deployment with the following considerations:

- **Scalability**: Containerized architecture allows for easy horizontal scaling
- **Security**: Environment-based configuration for sensitive data
- **Monitoring**: Comprehensive logging for production monitoring
- **Health Checks**: Built-in health check endpoints for load balancers

### AWS EC2 Deployment Ready

The project structure supports deployment on AWS EC2 instances with:
- Security group configurations for HTTP/HTTPS traffic
- SSH key-based access
- Docker installation scripts
- Automated backup strategies

## 🔧 Development

### Local Development Setup

1. **Set up Python environment**
   ```bash
   cd api
   pip install -r requirements.txt
   ```

2. **Database Setup**
   ```bash
   python setup.py  # Creates necessary tables
   ```

3. **Run locally**
   ```bash
   uvicorn api.main:app --reload --host 0.0.0.0 --port 8000
   ```

### Database Schema

The application automatically creates the following tables:
- `users` - User accounts
- `movies` - Movie catalog
- `genres` - Movie genres
- `reviews` - User movie reviews
- `watchlist` - User movie watchlists

## 📊 Monitoring & Logging

- **Application Logs**: Comprehensive logging to both console and file (`app.log`)
- **Access Logs**: Request/response logging via uvicorn
- **Error Handling**: Custom exceptions with proper HTTP status codes
- **Health Monitoring**: Status endpoint for uptime monitoring

## 🔐 Security Features

- **Input Validation**: Pydantic schemas for request validation
- **SQL Injection Prevention**: Parameterized queries
- **Error Handling**: Secure error messages without sensitive data exposure
- **Environment Variables**: Secure configuration management

## 📈 Performance Considerations

- **Connection Pooling**: Efficient database connection management
- **Async Support**: FastAPI's async capabilities for high concurrency
- **Containerization**: Optimized Docker images for fast startup times
- **Database Indexing**: Proper database schema with primary keys and relationships

## 🎯 DevOps Best Practices

This project demonstrates:

- **Infrastructure as Code**: Docker and Docker Compose configurations
- **Separation of Concerns**: Clear architectural boundaries
- **Environment Management**: Configuration through environment variables
- **Logging Strategy**: Structured logging for monitoring and debugging
- **Health Checks**: Monitoring endpoints for operational visibility

## 📚 Educational Context

This project was developed as part of the DevOps examination where we had to configure a development environment for an API at Utvecklarakademin, demonstrating:

- Server configuration and management
- Containerization strategies
- Database integration
- API development best practices
- Production deployment readiness

