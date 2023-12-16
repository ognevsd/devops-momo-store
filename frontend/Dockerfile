FROM node:16.20.1-slim as builder
WORKDIR /usr/src/app
COPY . .
RUN npm install
ENV NODE_ENV=dev
ENV VUE_APP_API_URL=/api
RUN npm run build

FROM nginx:latest
WORKDIR /usr/share/nginx/html
RUN apt update && apt install curl -y
COPY --from=builder /usr/src/app/dist/. /usr/share/nginx/html/
# COPY --from=builder /usr/src/app/default.conf /etc/nginx/conf.d
EXPOSE 80