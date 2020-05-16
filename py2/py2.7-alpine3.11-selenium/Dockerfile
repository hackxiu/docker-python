FROM python:2.7-alpine3.11

# update apk repo
RUN echo "http://dl-4.alpinelinux.org/alpine/v3.11/main" >> /etc/apk/repositories && \
    echo "http://dl-4.alpinelinux.org/alpine/v3.11/community" >> /etc/apk/repositories

# install chromedriver
RUN apk --no-cache -q -U update \
    && rm -rf /var/cache/apk/* \
    && rm -rf /var/lib/apt/lists/*
RUN apk --no-cache -q -U upgrade \
    && rm -rf /var/cache/apk/* \
    && rm -rf /var/lib/apt/lists/*
RUN apk --no-cache -q -U add bash vim chromium chromium-chromedriver

# upgrade pip
RUN pip install --upgrade pip

# install selenium
RUN pip install selenium
RUN echo "http://mirrors.aliyun.com/alpine/v3.11/main" >> /etc/apk/repositories \
    && echo "http://mirrors.aliyun.com/alpine/v3.11/community" >> /etc/apk/repositories \
    && cd ~ \
    && mkdir .pip
    
# pip aliyun
ADD pip.conf /root/.pip
