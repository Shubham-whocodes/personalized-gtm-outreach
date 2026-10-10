FROM python:3.12-slim

WORKDIR /app

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    PORT=8765 \
    PIP_DEFAULT_TIMEOUT=300 \
    PIP_RETRIES=10 \
    PIP_DISABLE_PIP_VERSION_CHECK=1

COPY requirements.txt pyproject.toml ./
COPY src ./src
COPY comparison ./comparison
COPY docs ./docs
COPY prompts ./prompts

# Large wheels (e.g. cryptography) can stall on slow links; long timeout + retries avoid flaky builds.
RUN --mount=type=cache,target=/root/.cache/pip \
    pip install --upgrade pip \
    && pip install --timeout 300 -r requirements.txt \
    && pip install --timeout 300 -e .

RUN useradd --create-home --uid 10001 appuser \
    && mkdir -p /data/runs \
    && chown -R appuser:appuser /data/runs

USER appuser

EXPOSE 8765

VOLUME ["/data/runs"]

CMD ["python", "-m", "provider_comparison.web", "--host", "0.0.0.0", "--data-dir", "/data/runs"]
