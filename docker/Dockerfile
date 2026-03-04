FROM python:3.12-slim

WORKDIR /app

# Install system dependencies for Pillow
RUN apt-get update && apt-get install -y --no-install-recommends \
    libjpeg62-turbo-dev libwebp-dev \
    && rm -rf /var/lib/apt/lists/*

COPY wine-tracker/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY wine-tracker/app/ .

VOLUME /data
ENV DATA_DIR=/data/wine-tracker

EXPOSE 5050
CMD ["python3", "app.py"]
