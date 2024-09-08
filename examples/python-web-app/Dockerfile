FROM ubuntu

# Set the working directory
WORKDIR /app

# Copy the requirements and application code
COPY requirements.txt /app
COPY devops /app

# Install Python, pip, and create a virtual environment
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv venv && \
    . venv/bin/activate && \
    venv/bin/pip install -r requirements.txt

# Set the entry point to use the virtual environment's Python
ENTRYPOINT ["./venv/bin/python"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
