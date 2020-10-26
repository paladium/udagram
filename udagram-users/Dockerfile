FROM node:13
WORKDIR /usr/src/app
COPY package*.json ./
#Install dependecies and build the app
RUN npm install
COPY . .
RUN npm run tsc
EXPOSE 8080
CMD ["node", "./www/server.js"]