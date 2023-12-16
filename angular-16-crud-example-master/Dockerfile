FROM node:20-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm install  @angular/cli@latest
RUN npm install   
COPY . .
RUN ng build
FROM nginx:1.25.3-alpine
COPY --from=build /app/dist/angular-16-crud/ /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
