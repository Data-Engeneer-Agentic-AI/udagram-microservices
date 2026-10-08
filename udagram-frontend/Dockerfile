FROM node:18 AS build

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install --force

COPY . .

RUN npm run build

FROM nginx:alpine

COPY --from=build /usr/src/app/www /usr/share/nginx/html

EXPOSE 80
