# Use a standard, slim Python base image
FROM python:3.10-slim

# Set the working directory inside the container
WORKDIR /app

# Install system dependencies required by OpenCV
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx \
    libglib2.0-0 \
&& rm -rf /var/lib/apt/lists/*

# Copy your requirements file first to leverage Docker's cache
COPY requirements.txt .

# Install your Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of your backend application code into the container
COPY . .

# Hugging Face Spaces run on port 7860 by default.
# We'll run Gunicorn (which is in your requirements.txt) on this port.
CMD ["gunicorn", "app:app", "--bind", "0.0.0.0:7860"]