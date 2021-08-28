FROM nginx:alpine

MAINTAINER Vladislav Borodin <vladislav_borodin@epam.com>

COPY $PWD/2048 /usr/share/nginx/html

ENTRYPOINT ["nginx", "-g", "daemon off;"]