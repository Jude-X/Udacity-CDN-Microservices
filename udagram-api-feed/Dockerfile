# Use NodeJS base image
FROM node:16-alpine

# Create app directory
WORKDIR /app

# Copy package.json and package-lock.json to app directory
COPY package*.json ./

# Install dependencies
RUN npm install 

# Copy source code to app directory
COPY . .

# Build the source code
RUN npm run build

# Bind the port that the image will run on
EXPOSE 8080

# Define the Docker image's behavior at runtime
CMD [ "npm", "start" ]
