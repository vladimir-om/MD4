FROM nginx:latest

RUN mkdir -p /usr/www/company.com

COPY ./company.com /usr/www/company.com
COPY ./conf/default.conf /etc/nginx/conf.d/default.conf
COPY ./conf/nginx.conf /etc/nginx/nginx.conf

RUN groupadd --gid 1000 vld \
  && useradd --uid 1000 --gid vld --shell /bin/bash --create-home vld \
  && chown -R vld:vld /usr/www/company.com \
  && chmod -R 754 /usr/www/company.com

CMD ["nginx", "-g", "daemon off;"]


