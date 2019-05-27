FROM tiangolo/uwsgi-nginx:python3.7

ENV UWSGI_INI /dash-example/uwsgi.ini
ENV LISTEN_PORT 8080
ENV NGINX_WORKER_PROCESSES auto
#ENV NGINX_WORKER_CONNECTIONS 1024
#ENV NGINX_WORKER_OPEN_FILES 1024

ENV UWSGI_CHEAPER 3
ENV UWSGI_PROCESSES 4
EXPOSE 8080 80 9191

WORKDIR /dash-example

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY app.py app.py
COPY assets assets
COPY uwsgi.ini uwsgi.ini
COPY wsgi.py wsgi.py