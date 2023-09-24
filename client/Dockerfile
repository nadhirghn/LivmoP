# Use an official Node.js runtime as the base image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app/client

# Copy package.json and package-lock.json to the container
COPY package*.json ./
RUN apk add --no-cache python3 make g++

# Install app dependencies
RUN npm install

# Copy the rest of the application code to the container
COPY . .

# Expose the port the app will run on
EXPOSE 3000

# Define the command to start your React application
CMD ["npm", "start"]
