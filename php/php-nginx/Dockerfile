FROM albertalvarezbruned/lamp:php


ENV DEBIAN_FRONTEND noninteractive

# Install Nginx.
RUN \
  add-apt-repository -y ppa:nginx/stable && \
  apt-get update && \
  apt-get install -y nginx && \
  rm -rf /var/lib/apt/lists/* && \
  chown -R www-data:www-data /var/lib/nginx

# Define working directory.
WORKDIR /etc/nginx
RUN apt-get clean

# Copy all config files
#COPY ./config/default.conf /etc/nginx/conf.d/default.conf
COPY ./nginx.conf /etc/nginx/nginx.conf

# Define default command.
CMD nginx
