FROM node:10.15-slim

ENV PATH /app/node_modules/.bin/:$PATH
ENV NODE_ENV=production

WORKDIR /app

COPY package.json package-lock*.json ./

RUN npm install && npm cache clean --force
COPY . .

CMD ["node", "./bin/www"]
