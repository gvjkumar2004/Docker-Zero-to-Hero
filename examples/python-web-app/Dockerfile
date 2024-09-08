FROM ubuntu

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install --user pipx && \
    python3 -m pipx ensurepath && \
    pipx install -r requirements.txt

ENTRYPOINT ["~/.local/bin/pipx", "run"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
