FROM node:latest

RUN mkdir -p /app

WORKDIR /app

COPY package.json /app

COPY yarn.lock /app

RUN yarn

COPY . /app

CMD ["yarn", "dev"]
