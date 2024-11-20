FROM node:20
EXPOSE 80:80
ENV DB_HOST="mysql"
RUN mkdir /app/server
WORKDIR /app/server
COPY package.json .
COPY *.js  .
RUN npm install 
CMD ["node" , "index.js"]