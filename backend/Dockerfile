FROM node:20 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install


FROM node:20.18.0-alpine3.20
EXPOSE 8080
ENV DB_HOST="mysql"
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/server && \
    chown -R expense:expense /opt/server
WORKDIR /opt/server
COPY --from=builder /opt/server /opt/server
USER expense
CMD ["node", "index.js"]


#befor multistage dicker file
# FROM node:20.18.0-alpine3.20
# EXPOSE 80:80
# ENV DB_HOST="mysql"
# RUN addgroup -S expense && adduser -S expense -G expense && \
#     mkdir /opt/server && \
#     chown -R expense:expense /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js  .
# RUN npm install 
# CMD ["node" , "index.js"]

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