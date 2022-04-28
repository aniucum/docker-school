FROM node:16 as builder
COPY ./frontend/. /app
WORKDIR /app
RUN yarn install && yarn build


FROM nginx:latest
WORKDIR /usr/share/nginx/html
RUN rm -rf ./*
COPY --from=builder --chown=nginx:nginx /app/build .
EXPOSE 80
