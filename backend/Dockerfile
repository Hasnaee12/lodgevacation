# Use an official Python runtime as a parent image
FROM python:3.8-slim
WORKDIR /app
COPY backend/requirements.txt .
# Install system dependencies and MySQL development libraries
RUN apt-get update && \
    apt-get install -y default-libmysqlclient-dev build-essential && \
    rm -rf /var/lib/apt/lists/*
# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt
# Copy the rest of the application code into the container
COPY backend /app
# Command to run the application
CMD ["python", "app.py"]