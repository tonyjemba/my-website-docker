FROM nginx:1.25.2-alpine


# install nano
RUN apk update && apk add nano

# remove default nginx config file
RUN rm -rf /etc/nginx/conf.d/default.conf

#use the config file into the default
COPY nginx.conf /etc/nginx/conf.d
