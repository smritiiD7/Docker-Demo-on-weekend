FROM python:3.12-slim

ARG ENVIRONMENT=dev
ENV APP_ENVIRONMENT=${ENVIRONMENT}

WORKDIR /app

COPY requirements.txt .
RUN pip install --upgrade pip && \
    pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org -r requirements.txt

COPY app.py .
RUN mkdir -p templates
COPY dev.html ./templates/
COPY qa.html ./templates/

CMD ["python", "app.py"]
