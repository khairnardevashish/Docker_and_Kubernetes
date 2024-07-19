FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

ENV MONGODB_USERNAME=dev
ENV MONGODB_PASSWORD=password

CMD ["npm", "start"]