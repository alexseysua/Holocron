FROM tiangolo/uvicorn-gunicorn-fastapi:python3.9-slim

WORKDIR /app

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV PYTHONPATH "${PYTHONPATH}:/app"

# copy requirements file
COPY requirements.txt  /app/requirements.txt

RUN set -eux \
	&& pip install --no-cache-dir uv \
    && uv pip install --no-cache --system -r /app/requirements.txt

# copy project
COPY app /app/app
