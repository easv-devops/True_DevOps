FROM node:20-alpine as angular
WORKDIR /ng-app
COPY Frontendv2/package*.json ./
RUN npm ci
COPY Frontendv2 .
RUN npm run build

FROM nginx:alpine
COPY --from=angular /ng-app/www /usr/share/nginx/html

EXPOSE 8080
