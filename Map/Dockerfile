FROM node:14.6.0-alpine3.10 as build-step
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . /app
RUN npm start

FROM nginx:1.17.1-alpine
COPY --from=build-step /app/docs /usr/share/nginx/html
