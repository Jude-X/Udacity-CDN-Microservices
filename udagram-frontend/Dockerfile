# Use NodeJS base image
FROM node:16-alpine as base

# Create app directory
WORKDIR /app

# Copy package.json and package-lock.json to app directory
COPY package*.json ./

# Install Ionic globally
RUN npm install -g ionic

# Install dependencies
RUN npm install

# Copy source code to app directory
COPY . .

# Build the source code
RUN npm run build

# Use Nginx base image
FROM nginx:alpine

# Delete files in the html directory
RUN rm -rf /usr/share/nginx/html/*

# Copy bundled code into the html directory
COPY --from=base /app/www/ /usr/share/nginx/html/