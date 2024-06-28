FROM python:slim 

WORKDIR /usr/src/django_airbnb_backend

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apt-get update && apt-get install -y netcat-traditional

RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

COPY ./entrypoint.sh .
RUN sed -i 's/\r$//g' /usr/src/django_airbnb_backend/entrypoint.sh
RUN chmod +x /usr/src/django_airbnb_backend/entrypoint.sh

COPY . .

ENTRYPOINT [ "/usr/src/django_airbnb_backend/entrypoint.sh" ]


