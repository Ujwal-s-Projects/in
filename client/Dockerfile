FROM node:14 AS build
WORKDIR /client
COPY . /client
RUN npm install && npm clean package --prod

FROM nginx:latest
COPY --from=build /client /usr/share/nginx/html/
COPY nginx.conf /etc/nginx/conf.d/default.conf 
EXPOSE 4200