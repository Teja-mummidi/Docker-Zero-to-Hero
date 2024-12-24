# Use the official Ubuntu base image
FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy application files
COPY requirements.txt /app/
COPY devops /app/devops/

# Install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install --no-cache-dir -r requirements.txt && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set the default command to run the application
ENTRYPOINT ["python3"]
CMD ["devops/manage.py", "runserver", "0.0.0.0:8000"]




