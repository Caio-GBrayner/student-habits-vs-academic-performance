FROM python:3.12-slim-bookworm

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .
COPY best_model.pkl .

EXPOSE 8501

CMD ["streamlit", "run", "app.py"]