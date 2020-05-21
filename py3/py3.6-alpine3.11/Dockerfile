FROM python:3.6-alpine3.11

# update apk repo
RUN repositories /etc/apk/

# install chromedriver
RUN apk --no-cache -q -U update \
    && rm -rf /var/cache/apk/* \
    && rm -rf /var/lib/apt/lists/*
RUN apk --no-cache -q -U upgrade \
    && rm -rf /var/cache/apk/* \
    && rm -rf /var/lib/apt/lists/*
RUN apk --no-cache -q -U add bash vim gcc musl-dev libxslt-dev libffi-dev libressl-dev chromium chromium-chromedriver

# upgrade pip
RUN pip install --upgrade pip \
    && pip install --upgrade setuptools
RUN echo "http://mirrors.aliyun.com/alpine/v3.11/main" >> /etc/apk/repositories \
    && echo "http://mirrors.aliyun.com/alpine/v3.11/community" >> /etc/apk/repositories \
    && cd ~ \
    && mkdir .pip
    
# pip aliyun
ADD pip.conf /root/.pip
