FROM nginx:1.25.2-alpine


# install nano
RUN apk update && apk add nano

#use the config file into the container
COPY nginx.conf /etc/nginx/nginx.conf
