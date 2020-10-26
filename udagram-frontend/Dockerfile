FROM node:13 as builder
WORKDIR /usr/src/app
COPY package*.json ./
#Install dependecies and build the app
RUN npm install
COPY . .
RUN npm run build -- --configuration production

FROM nginx:alpine
COPY --from=builder /usr/src/app/www/ /usr/share/nginx/html
COPY --from=builder /usr/src/app/nginx.conf /etc/nginx/nginx.conf