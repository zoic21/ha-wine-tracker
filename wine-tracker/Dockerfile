ARG BUILD_FROM
FROM $BUILD_FROM

# Install Python + pip deps
RUN apk add --no-cache python3 py3-pip py3-pillow ca-certificates \
    && update-ca-certificates
RUN pip3 install --force-reinstall requests urllib3 certifi --break-system-packages \
    && pip3 install flask anthropic openai --break-system-packages

# Copy app
WORKDIR /app
COPY app/ /app/

EXPOSE 5050
CMD ["python3", "app.py"]
