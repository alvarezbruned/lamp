FROM mysql:5.7
COPY ./my.cnf /etc/mysql/conf.d/
ENV TZ="Europe/Madrid"
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN export TZ="Europe/Madrid"
