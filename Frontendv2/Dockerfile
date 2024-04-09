FROM node:20-alpine as angular
WORKDIR /ng-app
COPY Frontendv2/package*.json ./
RUN npm ci
COPY Frontendv2 .
RUN npm run build

FROM nginx:alpine
COPY --from=angular /ng-app/dist/www/browser /usr/share/nginx/html
EXPOSE 80
