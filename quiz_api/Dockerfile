FROM node:19 AS build-env

WORKDIR /app

COPY package*.json ./

RUN npm i

COPY . .

FROM  gcr.io/distroless/base-debian10
COPY --from=build-env /app /app
WORKDIR /app

EXPOSE 5000

CMD ["npm","start"]