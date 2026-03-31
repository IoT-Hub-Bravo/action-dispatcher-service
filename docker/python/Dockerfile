FROM python:3.11-slim-bookworm

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PIP_DISABLE_PIP_VERSION_CHECK=1 \
    PIP_NO_CACHE_DIR=1

WORKDIR /app

RUN addgroup --gid 10001 --system python-user && \
    adduser --no-create-home --shell /bin/false \
    --disabled-password --uid 10001 --system --group python-user

COPY ./src/requirements.txt /app/requirements.txt

RUN python -m pip install --upgrade pip \
    && python -m pip install -r requirements.txt \
    && rm -rf /root/.cache

COPY --chown=python-user:python-user ./src/ /app/

USER python-user