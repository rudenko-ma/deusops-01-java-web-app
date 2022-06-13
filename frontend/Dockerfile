# syntax=docker/dockerfile:1

FROM node:14-alpine
ENV NODE_ENV development
WORKDIR /app

COPY package.json .
RUN npm install

COPY . .
EXPOSE 3000
CMD [ "npm", "run", "start" ]
