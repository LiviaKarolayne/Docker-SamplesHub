FROM python:3.7-alpine

WORKDIR /app
COPY ./requirements.txt /tmp
RUN pip install -r /tmp/requirements.txt -v
EXPOSE 5000
CMD flask run -h "0.0.0.0" --reload
