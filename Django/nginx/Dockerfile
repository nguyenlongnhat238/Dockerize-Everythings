FROM nginx:1.25

RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d
# create folder for certificates
RUN mkdir -p /etc/nginx/example.com/

# copy folder certificates
COPY example.com/* /etc/nginx/example.com/
