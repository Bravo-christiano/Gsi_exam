   FROM ubuntu:latest

   RUN apt-get update && apt-get install -y nginx

   RUN echo "<html><body><h1>Hello, World!</h1></body></html>" > /var/www/html/index.html

   EXPOSE 80

   CMD ["nginx", "-g", "daemon off;"]
