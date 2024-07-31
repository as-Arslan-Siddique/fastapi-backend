# Baseline FastAPI App

Welcome to my baseline FastAPI app! This application is designed to be easy to use and is based on Docker Compose. Follow the instructions below to get started quickly.

## Features

- **FastAPI**: A modern, fast (high-performance) web framework for building APIs with Python 3.7+.
- **Docker Compose**: Simplifies running the app in a containerized environment.
- **JWT Authentication**: Secure your API endpoints with JSON Web Tokens (JWT).

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed on your machine:

- **Docker**: [Download and install Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Download and install Docker Compose](https://docs.docker.com/compose/install/)

### Environment Variables

Make sure the following environment variables are set in your environment:

```bash
appsecret="TEST(W&DHQ_@?S2y92897H({w.qj"
userid="ec391fb6-d40f-40b2-be76-14be580a6b81"
username="dev"
password="$2a$10$0WEY66JJM4dFvmYZq37/X.fAIZwGq.olZ/B7JS7H1FFQWw0dE0Bq." # password: "password" as string
```

### Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/fastapi-backend.git
   cd fastapi-backend
   ```

2. **Run the Application**:

   ```bash
   docker compose up
   ```

3. **Access the API Documentation**:

   Open your web browser and navigate to:

   ```
   http://localhost:8000/docs
   ```

### Authentication

To access secured API endpoints, you will need to authenticate. Use the following credentials to obtain an access token:

- **Username**: `dev`
- **Password**: `password`

Once authenticated, you will receive an access token that can be used to validate API requests.

### Example Authentication Function

Here's an example of the `authenticate` function used to validate tokens:

```python
import os
import jwt

def authenticate(token):
    try:
        appsecret = os.environ["appsecret"]
        payload = jwt.decode(token, appsecret)
        return {"data": payload}
    except Exception as e:
        return None
```

## Usage

With the access token obtained from the authentication process, you can now make requests to the secured endpoints of your FastAPI application.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request if you have any improvements or new features you'd like to add.

## Contact

For any questions or inquiries, please contact me at as.arslansiddique@gmail.com.
