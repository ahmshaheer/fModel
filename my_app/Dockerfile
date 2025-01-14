# Use an official Python runtime image as a base image
FROM python:3.9-slim

# Set the working directory
WORKDIR /my-app

# Install system dependencies (e.g., for PyTorch)
RUN apt-get update && apt-get install -y \
    libopenblas-dev \
    libomp-dev \
    && apt-get clean

# Copy the requirements.txt file and install Python dependencies
COPY my-app/requirements.txt /my-app/requirements.txt
RUN pip install --no-cache-dir -r /my-app/requirements.txt

# Copy the entire 'my-app' directory into the container
COPY my-app /my-app

# Ensure the 'my-app' directory is included in the Python path
ENV PYTHONPATH=/my-app

# Expose the port for your application
EXPOSE 8080

# Command to run the server
CMD ["python", "/my-app/my_app/server_app.py"]
