FROM node:lts-alpine as build-step
RUN mkdir -p /app
RUN npm install
COPY package.json /app
COPY . /app
CMD ["npm" , "start"]

FROM nginx:1.17.1-alpine
COPY --from=build-step /app/dist/* /usr/share/nginx/html
