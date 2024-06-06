FROM python:3.9-slim-buster

RUN apt-get update && apt-get install -qq -y \
    build-essential libpq-dev --no-install-recommends

ENV INSTALL_PATH /todo

RUN mkdir -p ${INSTALL_PATH}
RUN mkdir -p /var/log/todo

WORKDIR ${INSTALL_PATH}

COPY requirements.txt requirements.txt

RUN pip install --upgrade pip
RUN pip install -r requirements.txt


COPY . .

EXPOSE 8000

ENV FLASK_APP=app.py


CMD ["python", "app.py"]
