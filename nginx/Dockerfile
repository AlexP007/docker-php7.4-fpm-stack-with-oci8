FROM nginx:1.17

MAINTAINER AlexP007

ADD conf/nginx.conf /etc/nginx/

# comment undrelying line if use bitrix
ADD conf/default.conf /etc/nginx/conf.d/

# uncomment undrelying line if use bitrix
# ADD conf/bitrix.conf /etc/nginx/conf.d/

ADD conf/upstream.conf /etc/nginx/conf.d/

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80 443
