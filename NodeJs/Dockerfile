# syntax=docker/dockerfile:experimental
FROM node:19-buster-slim

# Create app directory
WORKDIR /usr/src/app

# copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy app source code
COPY . .

# expose port
EXPOSE 3000

# Start app
CMD ["npm", "start"]
