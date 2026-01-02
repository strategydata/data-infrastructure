FROM python:3.13.1

# Install system dependencies, development tools
# Combines all installations in a single layer and includes cleanup to minimize image size
RUN apt-get update && \
    # Install packages
    apt-get update && \
    apt-get install -y --no-install-recommends \
    wget \
    curl \
    git && \
    # Clean up
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /root/.cache/pip/*

# Copy and install Python requirements
COPY requirements.txt ./
RUN pip install --no-cache-dir -U pip && \
    pip install --no-cache-dir -r requirements.txt