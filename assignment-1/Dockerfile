FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY main.py .

ENTRYPOINT ["uvicorn"]
EXPOSE 80
CMD ["main:app", "--host", "0.0.0.0", "--port", "80"]
