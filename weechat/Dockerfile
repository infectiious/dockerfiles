# Header
FROM alpine
MAINTAINER Infectiious

# Environment
ENV LANG C.UTF-8
ENV HOME /weechat
ENV TERM xterm

# Install base packages. 
RUN apk update
RUN apk upgrade
RUN apk add curl
RUN apk add screen
RUN apk add tmux
RUN apk add wget
RUN apk add bash

# Install weechat
RUN apk add weechat

# Clean APK cache
RUN rm -rf /var/cache/apk/* 

# Create user
RUN mkdir -p $HOME/.weechat\
    && addgroup weechat\
    && adduser -h $HOME -D -s /bin/bash -G weechat weechat\ 
    && chown -R weechat:weechat $HOME
RUN mkdir -p $HOME/.weechat

# Entrypoint
COPY ./weechat-entrypoint.sh /

# User
WORKDIR $HOME

# Run weechat
ENTRYPOINT ["/weechat-entrypoint.sh"]
