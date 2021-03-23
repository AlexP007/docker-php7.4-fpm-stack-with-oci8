FROM nginx:1.18

MAINTAINER AlexP007

ADD nginx.conf /etc/nginx/
ADD upstream.conf /etc/nginx/conf.d/

# comment undrelying line if use bitrix
ADD default.conf /etc/nginx/conf.d/

# uncomment undrelying line if use bitrix
# ADD bitrix.conf /etc/nginx/conf.d/

RUN usermod -u 1000 www-data

CMD ["nginx", "-g", "daemon off;"]

EXPOSE 80 443
