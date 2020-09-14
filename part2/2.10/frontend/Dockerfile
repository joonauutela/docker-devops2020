FROM ubuntu:16.04

ENV API_URL=http://192.168.99.100:8000

# Install dependencies and clone repository
RUN apt-get update && apt-get install -y curl && apt-get install -y git
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN node -v && npm -v
RUN git clone https://github.com/docker-hy/frontend-example-docker

# Go into repo directory and install package.json dependencies
WORKDIR /frontend-example-docker
RUN npm install
RUN npm run build
RUN npm install -g serve

EXPOSE 5000

ENTRYPOINT ["/usr/bin/serve"]
CMD ["-s", "-l", "5000", "dist"]