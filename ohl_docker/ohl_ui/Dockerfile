#Dockerfile for ohl_ui

FROM node:13-buster-slim

ENV APP_HOME /ohl/ohl_ui
RUN mkdir -p $APP_HOME
# set working directory
WORKDIR $APP_HOME
# add `/ohl/ohl_ui/node_modules/.bin` to $PATH
ENV PATH /ohl/ohl_ui/node_modules/.bin:$PATH
RUN echo "$PWD"
COPY ./ohl_ui/package.json .

# install and cache app dependencies
RUN npm install
RUN npm install @vue/cli@4.1.1 -g

# start app
CMD ["npm", "run", "serve"]