FROM ubuntu:24.04

RUN apt-get update -y && apt-get install -y python3 python3-pip python3-venv && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN python3 -m venv /app/venv

ENV PATH="/app/venv/bin:$PATH"

RUN pip install flask==2.3.3

RUN useradd -m -u 1001 appuser

USER appuser

WORKDIR /app

COPY app.py .

EXPOSE 8080

CMD ["python3", "app.py"]
