# Stage 1: Build dependencies (Large Base Image) 994mb~1.01Gb
FROM python:3.7 AS builder

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

# Stage 2: Final Base Image 125mb~140mb (Slim Base Image)
FROM python:3.7-slim

WORKDIR /app

# Fix the incorrect path (use /usr/local/lib)
COPY --from=builder /usr/local/lib/python3.7/site-packages/ /usr/local/lib/python3.7/site-packages/

COPY . .

ENTRYPOINT ["python", "run.py"]

