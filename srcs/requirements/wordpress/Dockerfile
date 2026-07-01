# a Dockerfile is like a recipe that tells Docker how to build the imgae 

# what base image to start with
FROM debian:12
# files to copy from host to container
COPY index.html /home/yuwu/42/Inception/srcs/wordpress/index.html/
# nginx provide the web
RUN apt update && apt install -y nginx
# Document which port the container uses (just document!)
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]