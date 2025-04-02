FROM python:3.9-slim

WORKDIR /app

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    git \
    && rm -rf /var/lib/apt/lists/*

# Install LangFlow
RUN pip install --no-cache-dir langflow

# Copy local code to the container
COPY . .

# Set the port the app runs on
EXPOSE 8080

# Set environment variables
ENV LANGFLOW_HOST=0.0.0.0
ENV LANGFLOW_PORT=8080
ENV LANGFLOW_LOG_LEVEL=info
ENV LANGFLOW_DATABASE_URL=postgresql://api-ykhb76fGV2wQy1i:mixdaz-siBjuw-vakza7@34.35.30.117/langflow

# Run the application
CMD ["langflow", "run"]