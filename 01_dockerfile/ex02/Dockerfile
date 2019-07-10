FROM ruby

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install sqlite3
RUN gem install rails

ONBUILD EXPOSE 3000

ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install

ONBUILD RUN rails db:migrate && rails db:seed