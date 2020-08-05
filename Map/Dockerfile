FROM node:14.6.0-alpine3.10 as build-step
WORKDIR /app
COPY . ./app
RUN npm install
RUN npm start

FROM nginx:1.17.1-alpine
COPY --from=build-step /app/dist/Map /usr/share/nginx/html
