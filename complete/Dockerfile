FROM node:20 AS BUILD

WORKDIR /app

COPY blog .
RUN rm -rf .cache
RUN rm -rf public
RUN rm -rf node_modules

RUN npm install -g gatsby-cli
#RUN npm ci --legacy-peer-deps
RUN npm install --legacy-peer-deps
RUN gatsby build #--verbose

FROM nginx:alpine

COPY --from=build /app/public /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]