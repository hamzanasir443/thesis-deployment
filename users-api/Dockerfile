FROM node:14-alpine

WORKDIR /app

COPY package.json .

COPY . .

EXPOSE 8080

CMD [ "node", "users-app.js" ]