FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

ENV USERNAME=root
ENV PASSWORD=password


CMD ["npm", "start"]