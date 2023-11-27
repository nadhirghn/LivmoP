# Use an official Node.js runtime as the base image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app/client

# Copy package.json and package-lock.json to the container
COPY package*.json ./
RUN apk add --no-cache python3 make g++

# Install app dependencies
RUN npm install

# Install necessary tools or dependencies
RUN apk update && apk add --no-cache curl

# Health check command
HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD curl --fail http://34.173.2.98:8443 || exit 1

# Copy the rest of the application code to the container
COPY . .

# Expose the port the app will run on
EXPOSE 4000

# Define the command to start your React application
CMD ["npm", "start"]
