# Use an official Python image
FROM python:3.10

# Set the working directory inside the container
WORKDIR /app

# Copy only requirements.txt (NOT venv)
COPY ../requirements.txt .

# Install dependencies inside the container
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Copy the application code (excluding venv)
COPY . .

# Expose the Chainlit port (default: 8000)
EXPOSE 8000

# Start the Chainlit application
ENTRYPOINT ["python", "-m", "chainlit", "run", "app.py", "-h", "0.0.0.0", "-p", "8000"]
