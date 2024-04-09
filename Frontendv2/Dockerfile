FROM node:18.13.0 as build

WORKDIR /app

COPY Frontendv2/package.json ./
COPY Frontendv2/package-lock.json ./

RUN npm install
RUN npm install -g @angular/cli

COPY . .

WORKDIR /app/Frontendv2  # Change directory to your Angular project

RUN ng build

FROM nginx:latest

COPY --from=build /app/Frontendv2/www/aftas-angular /usr/share/nginx/html

EXPOSE 80
