FROM node:16-alpine AS builder
WORKDIR "/opt/app"
COPY ./package.json ./
RUN npm install
COPY ./ ./
RUN npm run build 
CMD ["npm", "run", "build"]

FROM nginx:latest
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /opt/app/build /usr/share/nginx/html