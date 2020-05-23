FROM python:2.7-alpine3.11

# update apk repo
ADD repositories /etc/apk/

# install chromedriver
RUN apk --no-cache -q -U update \
    && rm -rf /var/cache/apk/* \
    && rm -rf /var/lib/apt/lists/*
RUN apk --no-cache -q -U upgrade \
    && rm -rf /var/cache/apk/* \
    && rm -rf /var/lib/apt/lists/*
RUN apk --no-cache -q -U add bash vim gcc g++ make musl-dev libxslt-dev libffi-dev libressl-dev chromium chromium-chromedriver

# upgrade pip
RUN pip install --upgrade pip \
    && pip install --upgrade setuptools
RUN cd ~ \
    && mkdir .pip
    
# pip aliyun
ADD pip.conf /root/.pip/
