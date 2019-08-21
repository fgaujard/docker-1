FROM ruby:latest

ONBUILD RUN apt-get update -y &&\
            apt-get upgrade -y
ONBUILD RUN apt-get install build-essential libpq-dev nodejs sqlite3 -y

ONBUILD EXPOSE 3000

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN bundle exec rake db:migrate
ONBUILD RUN bundle exec rake db:seed

# docker build -t ft-rails:on-build .