## Traditional Build
FROM python:3.7

COPY ./requirements.txt /tmp
RUN pip install -r /tmp/requirements.txt -v
WORKDIR /app
COPY . .
EXPOSE 5000
ENV FLASK_ENV=development
CMD flask run -h "0.0.0.0"

