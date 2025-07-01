#fetching the base image
FROM python:3.12-slim

WORKDIR /app

COPY *.py .


RUN pip install --no-cache-dir --trusted-host pypi.org --trusted-host files.pythonhosted.org flask



ENV USER=Smriti
ENV GROUP=pythongroup

RUN groupadd -r ${GROUP} && useradd -m -r -g ${GROUP} ${USER}

RUN chown -R ${USER}:${GROUP} /app

USER ${USER}

CMD ["python", "app.py"]


#Exposing the python app to the host, so the python app is accessible externally
EXPOSE 5000 