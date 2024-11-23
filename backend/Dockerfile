FROM node:20.18.0-alpine3.20
EXPOSE 80:80
ENV DB_HOST="mysql"
RUN mkdir /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js  .
RUN npm install 
CMD ["node" , "index.js"]

# befror best practice
# FROM node:20
# EXPOSE 80:80
# ENV DB_HOST="mysql"
# RUN mkdir /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js  .
# RUN npm install 
# CMD ["node" , "index.js"]