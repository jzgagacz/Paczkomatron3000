FROM python:3.8-slim
RUN mkdir /app
WORKDIR /app
ADD requirements.txt /app
RUN pip3 install -r requirements.txt
ADD . /app
EXPOSE 8000
ENTRYPOINT ["gunicorn", "-w", "4", "--certfile", "cert.pem", "--keyfile", "key.pem", "-b", "0.0.0.0:8000", "app:app"]