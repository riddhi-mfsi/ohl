# Dockerfile for ohl_api

FROM ruby:2.6.5-slim-buster

# Install Ruby and MySQL-Client
RUN apt-get update \
 && apt-get install -qq -y --no-install-recommends \
    build-essential \
    nodejs \
    default-libmysqlclient-dev \
    libpq-dev \
    tzdata \
    libxml2-dev \
    libxslt-dev \
    ssh \
 && rm -rf /var/lib/apt/lists/*RUN nodejs -v
 
ENV APP_HOME /ohl/ohl_api
RUN mkdir -p $APP_HOME 
WORKDIR $APP_HOME
COPY ./ohl_api/Gemfile .
COPY ./ohl_api/Gemfile.lock ${APP_HOME}

RUN bundle install
COPY ./ohl_api ${APP_HOME}