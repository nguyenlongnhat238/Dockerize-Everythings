FROM node:18.20-bullseye as build
ARG ENV=testing
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install -g @angular/cli@15.2.1 --force && npm install --force
COPY . .
# RUN ng build
# RUN ng build --prod --configuration=$ENV
RUN echo "Building for $ENV"
RUN ng build --configuration=$ENV

FROM nginx:1.19.6 as nginx_fo
COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build /usr/src/app/dist/<project name> /usr/share/nginx/html/
EXPOSE 80