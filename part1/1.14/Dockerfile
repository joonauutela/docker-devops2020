FROM ruby:2.6.0

RUN apt-get update && apt-get install -y curl git

# Install node
RUN curl -sL https://deb.nodesource.com/setup_10.x
RUN apt install -y nodejs

# Clone, install and set up application
RUN git clone https://github.com/docker-hy/rails-example-project
WORKDIR /rails-example-project

RUN gem install bundler
RUN bundle install
RUN rails db:migrate

EXPOSE 3000

CMD ["rails", "s"]