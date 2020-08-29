FROM ubuntu:16.04

WORKDIR /app
RUN apt-get update && apt-get install -y curl

COPY script.sh .
CMD ["./script.sh"]