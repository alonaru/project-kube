# project-kube

## Docker Setup Instructions

This project contains a Python application and a Dockerfile for containerized deployment.

### Prerequisites

- Docker installed on your machine
- Python application files and `requirements.txt` present in the project directory

### How to Build the Docker Image

1. Open a terminal and navigate to the project directory.
2. Build the Docker image:
   ```bash
   docker build -t aws-flask-app .
   ```

### How to Run the Docker Container

1. Run the container, passing any required environment variables (e.g., AWS credentials):
   ```bash
   docker run -e AWS_ACCESS_KEY_ID=your_key -e AWS_SECRET_ACCESS_KEY=your_secret -p 5001:5001 aws-flask-app
   ```
   - Replace `your_key` and `your_secret` with your actual AWS credentials.

2. Access the application in your browser:
   ```
   http://<host_ip>:5001/
   ```

### Notes

- Make sure port 5001 is open on your host machine or cloud instance.
- The Dockerfile uses multi-stage builds for a minimal image.
- The application will start automatically when the container runs.
