FROM node:14 
WORKDIR /src/app
COPY package*.json ./
RUN npm install -g ionic
RUN npm install
COPY ./ ./
EXPOSE 8080