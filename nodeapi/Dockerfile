FROM node:14 AS build 
WORKDIR /nodeapp 
COPY . /nodeapp 
RUN npm install && npm clean package 

FROM node:14
COPY --from=build /nodeapp /node
EXPOSE 5000
CMD ["/bin/bash","-c","cd /node/ && npm start"]