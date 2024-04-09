FROM node:20.12.1

WORKDIR /app

COPY Frontend/package*.json ./

RUN npm install

RUN npm install -g @angular/cli

COPY Frontendv2 .

RUN ng build

FROM nginx:latest

COPY --from=build app/www/aftas-angular /usr/share/nginx/html

EXPOSE 80
