FROM node:21 AS backend-builder

WORKDIR /app

COPY package*.json ./

RUN npm i

COPY . .

FROM node:21-slim

COPY --from=backend-builder /app .

COPY ./config/config.env .env

EXPOSE 4000

CMD [ "npm", "start" ]

