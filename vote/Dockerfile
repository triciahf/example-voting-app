FROM python:2.7-alpine

WORKDIR /app
COPY requirements.txt .
COPY pip.conf /etc/pip.conf
RUN pip install -r requirements.txt

EXPOSE 80
CMD gunicorn app:app -b 0.0.0.0:80

# CMD sh
# docker build . -t vote:v1 --network="host"