FROM node:24-apline
COPY . /opt/
WORKDIR /opt 
RUN npm install && npm run build 
RUN apk update && apk add apache2 
RUN rm -rf /var/www/localhost/htdocs/* 
RUN cp -rf dist/* /var/www/localhost/htdocs 
EXPOSE 80 
ENTRYPOINT ["httpd", "-D" , "FOREGROUND"]
