FROM node:18.18.2-alpine3.17  as build-stage

# make it the working directory
WORKDIR /var/www/portfolio

# copy everthing to the working directory
COPY . .

# install npm packages
RUN npm install

#build the project
RUN npm run generate

#remove node modules after building
RUN rm -rf node_modules

#final image that will include the build files
FROM node:18.18.2-alpine3.17 as prod-stage

# make it the working directory
WORKDIR /var/www/portfolio

COPY --from=build-stage /var/www/portfolio/.output  ./.output/

#  runing the static files
CMD [ "npx", "serve", ".output/public" ]
