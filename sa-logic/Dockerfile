FROM python:3.6.6-alpine
RUN apk --update add python py-pip openssl ca-certificates py-openssl wget \
    && apk --update add --virtual build-dependencies libffi-dev openssl-dev python-dev py-pip build-base \
    && pip install --upgrade pip

COPY sa /app
WORKDIR /app

RUN pip3 install -r requirements.txt \
    && python3 -m textblob.download_corpora
EXPOSE 5000
ENTRYPOINT ["python3"]
CMD ["sentiment_analysis.py"]
