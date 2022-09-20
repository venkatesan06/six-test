FROM node AS Build
COPY . /app
WORKDIR /app
RUN npm install
RUN npm run build

FROM nginx
WORKDIR  /usr/share/nginx/html
RUN rm -rf *
COPY --from=Build /app/build .
