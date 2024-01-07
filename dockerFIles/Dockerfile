FROM ruby:3.1.2 AS rubydocker

# throw errors if Gemfile has been modified since Gemfile.lock
#RUN bundle config --global frozen 1
RUN apt-get update
RUN apt-get -y install nodejs npm

COPY . /usr/src/app

WORKDIR /usr/src/app

RUN bundle install
RUN npm install


ENTRYPOINT rails db:create && rails db:migrate && rails server -b 0.0.0.0 -p 3000