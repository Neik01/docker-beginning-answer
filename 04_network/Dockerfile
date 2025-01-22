FROM node:latest

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
EXPOSE 3000

ENV DB_HOST=mysql-db
ENV DB_USER=root
ENV DB_PASSWORD=root
ENV DB_NAME=testdb

CMD ["npm", "start"]