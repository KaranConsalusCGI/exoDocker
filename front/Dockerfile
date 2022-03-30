FROM node:14.15 AS build
WORKDIR /app
COPY ./package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx:latest
COPY --from=build /app/dist/express-gaumont /usr/share/nginx/html
