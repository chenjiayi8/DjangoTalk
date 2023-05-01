FROM ubuntu:22.04


# replace shell with bash so we can source files
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# environment variables
ENV TZ=UTC
# timezone
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
# user
RUN useradd ubuntu --create-home -m -s /bin/bash

WORKDIR /app

RUN apt update
RUN apt install python3 python3-pip tzdata -y
RUN apt install bash git nodejs -y


COPY requirements.txt . 



RUN pip3 install -r requirements.txt
# && apt install python3 py3-pip -y

# COPY requirements.txt .

# RUN apk add --no-cache build-base \
#     && pip install --no-cache-dir -r requirements.txt \
#     && apk del build-base

USER ubuntu

EXPOSE 8000

