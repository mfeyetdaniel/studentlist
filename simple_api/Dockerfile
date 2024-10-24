FROM python:3.8-buster AS base
LABEL maintainer="DanielMfeyet"
RUN apt update -y && apt install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y
FROM base as src
WORKDIR /root
COPY student_age.py .
COPY requirements.txt .
RUN pip3 install -r requirements.txt
RUN mkdir -p data
FROM src as prod
EXPOSE 5000
CMD [ "python3", "./student_age.py" ]
