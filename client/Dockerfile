FROM node:16 AS build
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
RUN npm run build
#STEP 2 build docker image
FROM nginx:1.19.0-alpine AS prod-deploy
COPY --from=build app/dist usr/share/nginx/html
EXPOSE 80
