# Stage 1: Build the React app
FROM node:22-bullseye AS build

WORKDIR /app

# # Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# # Copy the rest of the app's source code
COPY . .

# Build the app
RUN npm run build

# EXPOSE 3000

# CMD ["npm", "run", "preview"]

# Stage 2: Serve the app with Nginx
FROM nginx:1.26.0

# Copy the built app from the previous stage
COPY --from=build /app/dist /usr/share/nginx/html

# # Copy the Nginx configuration file
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]