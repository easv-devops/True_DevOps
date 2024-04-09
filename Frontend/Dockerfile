# Stage 1: Build the Angular app
FROM node:14 

# Copy package.json and package-lock.json to the working directory
COPY ./home/azureuser/True_Devops/Frontend/package.json ./
COPY ./home/azureuser/True_Devops/Frontend/package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the Angular app for production
RUN npm run build

# Stage 2: Serve the Angular app using Nginx
FROM nginx:alpine

# Copy the built Angular app from the previous stage to the nginx public directory
COPY --from=builder /app/www /usr/share/nginx/html

# Copy the nginx configuration file to enable Angular HTML5 mode routing
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Command to start Nginx
CMD ["nginx", "-g", "daemon off;"]