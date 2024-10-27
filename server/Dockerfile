FROM node:14.14.0-alpine
WORKDIR /opt/app
COPY ./package.json ./
RUN npm install
COPY ./ ./
CMD ["npm", "run", "start"]