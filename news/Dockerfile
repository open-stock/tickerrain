FROM ubuntu:20.04

RUN apt-get update -y
RUN apt-get install software-properties-common -y
RUN apt-add-repository universe
RUN apt-get update
RUN apt-get install -y python3-pip python-dev build-essential
RUN apt-get install libpangocairo-1.0-0 -y
RUN apt-get install git -y

WORKDIR /app

COPY ./news .

COPY requirements.txt .

RUN pip3 install -r requirements.txt

RUN python3.8 -m spacy download en_core_web_sm

CMD python3.8 news.py $REDDIT_CLIENT_ID $REDDIT_SECRET $REDDIT_USERNAME $REDDIT_PASSWORD