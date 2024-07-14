FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

ARG DEFAULT_PORT=80
#Defining an Env variable
ENV PORT=$DEFAULT_PORT

EXPOSE $PORT

CMD [ "npm", "start" ]