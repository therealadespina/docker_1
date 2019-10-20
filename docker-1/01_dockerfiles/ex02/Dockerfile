FROM ruby
LABEL maintainer="adespina@student.21-school.ru"
RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3
ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# How to build it?
# docker build -t ft-rails:on-build .

#1 docker build -t ft-rails:on-build . — Build an image from your Dockerfile
#2 docker build -t ex02 . — Build an image from Dockerfile provided by task
#3 docker run -it --rm -p 3000:3000 ex02 — Run created image
#4 say = "" how to proof it
