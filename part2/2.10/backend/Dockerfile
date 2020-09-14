FROM ubuntu:16.04

ENV FRONT_URL=http://192.168.99.100:5000

# Install dependencies and clone github repo
RUN apt-get update && apt-get install -y curl && apt-get install -y git
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs
RUN git clone https://github.com/docker-hy/backend-example-docker

# Go into repo directory and install package.json dependencies
WORKDIR /backend-example-docker
RUN npm install

EXPOSE 8000

CMD npm start