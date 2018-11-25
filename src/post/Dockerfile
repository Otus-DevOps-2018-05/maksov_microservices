FROM python:3.6.0-alpine


ENV POST_DATABASE_HOST post_db
ENV POST_DATABSE posts

WORKDIR /app
COPY . /app

RUN apk update \
  			   && apk add --no-cache build-base \
  			   && pip install --upgrade pip \
  			   && pip install -r /app/requirements.txt 

ENTRYPOINT ["python3", "post_app.py"]