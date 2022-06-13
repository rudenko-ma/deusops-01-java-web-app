# syntax=docker/dockerfile:1

FROM node:14-alpine AS builder
ENV NODE_ENV production
WORKDIR /build

COPY package.json .
RUN npm install

COPY . .
RUN npm run-script build


FROM nginx:1.21.0-alpine
COPY --from=builder /build/build /usr/share/nginx/html