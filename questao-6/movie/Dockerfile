FROM node:16-alpine3.15
WORKDIR /app
COPY ./src/package* ./
RUN npm install
COPY ./src/ .
EXPOSE 8181
CMD ["node", "server.js"]
