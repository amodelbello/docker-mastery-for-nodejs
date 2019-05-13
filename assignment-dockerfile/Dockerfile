FROM node:10.15-alpine
EXPOSE 3000

RUN apk add --no-cache tini

WORKDIR /node
COPY package*.json ./
RUN mkdir app && chown -R node:node .
USER node
RUN npm install && npm cache clean --force

WORKDIR /node/app
COPY --chown=node:node . .

ENTRYPOINT ["/sbin/tini", "--"]
CMD ["node", "app.js"]
