FROM node:16-alpine AS build
WORKDIR /src
COPY ["package*.json", "/src/"]
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /src/dist/frontend /usr/share/nginx/html
