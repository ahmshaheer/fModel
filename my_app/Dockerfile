FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy the requirements file
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of your application code
COPY . ./

# Expose the port
EXPOSE 8080

# Command to run the application
ENTRYPOINT ["python", "server.py"]

