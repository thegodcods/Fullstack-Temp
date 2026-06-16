# Gunakan image dasar Python
FROM python:3.12-slim

# Set variabel lingkungan
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Set direktori kerja
WORKDIR /code

# Salin file requirements.txt dan pasang dependensi
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Salin seluruh kode sumber backend
COPY . .

# Expose port 7860 (Hugging Face default)
EXPOSE 7860

# Jalankan aplikasi dengan gunicorn pada port 7860
CMD ["gunicorn", "app:app", "--bind", "0.0.0.0:7860"]