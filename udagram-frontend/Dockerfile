FROM node:15 AS build
RUN mkdir /build
WORKDIR /build
COPY . ./
RUN npm install -g ionic
RUN npm install
RUN ionic build

FROM nginx:1.18
RUN rm -fr /usr/share/nginx/html/{*,.??*}
COPY --from=build /build/www/* /usr/share/nginx/html/

