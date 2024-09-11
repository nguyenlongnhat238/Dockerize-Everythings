# syntax=docker/dockerfile:experimental
FROM node:20.17-bullseye

# set work directory
WORKDIR /usr/src/app

# copy package.json and package-lock.json
COPY package*.json ./

# install dependencies
RUN npm install

# copy app
COPY . .

# build app
RUN npm run build

# start app
CMD [ "npm", "start" ]

# expose port
EXPOSE 3000
