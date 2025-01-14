# Use an official Python runtime image as a base image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Install system dependencies (e.g., PyTorch)
RUN apt-get update && apt-get install -y \
    libopenblas-dev \
    libomp-dev \
    && apt-get clean

# Copy the requirements.txt and install the dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code into the container
COPY . .

# Ensure the current directory is in the Python path
ENV PYTHONPATH=/app

# Expose the port if needed
EXPOSE 8080

# Command to run your server
CMD ["python", "server.py"]
