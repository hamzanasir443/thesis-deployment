FROM node:14-alpine

WORKDIR /app

COPY package.json .

RUN npm install \
curl -fsSLO https://get.docker.com/builds/Linux/x86_64/docker-17.04.0-ce.tgz \
&& tar xzvf docker-17.04.0-ce.tgz \
&& mv docker/docker /usr/local/bin \
&& rm -r docker docker-17.04.0-ce.tgz

COPY . .

EXPOSE 8080

CMD [ "node", "users-app.js" ]