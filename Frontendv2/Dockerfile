# Stage 1: Build the Angular app
FROM node:20 as builder

# Set the working directory inside the container
WORKDIR /app

# Copy the Angular project files to the working directory
COPY Frontendv2 .

# Install Angular CLI globally
RUN npm install -g @angular/cli

# Install dependencies
RUN npm install

# Build the Angular app for production
RUN ng build

# Stage 2: Serve the Angular app using http-server
FROM node:alpine

# Install http-server globally
RUN npm install -g http-server

# Set the working directory inside the container
WORKDIR /app

# Copy the built Angular app from the previous stage to the working directory
COPY --from=builder /app/www /app

# Expose port 8080 (or any other port you prefer)
EXPOSE 8080
