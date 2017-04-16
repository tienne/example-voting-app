# build:
#   docker build --force-rm=true -f Dockerfile -t subicura/sample_result:1 .
# run:
#   docker run --rm -p 3000:80 subicura/sample_result:1

FROM node:5.11.0-slim

WORKDIR /app

RUN npm install -g nodemon
ADD package.json /app/package.json
RUN npm config set registry http://registry.npmjs.org
RUN npm install && npm ls
RUN mv /app/node_modules /node_modules

ADD . /app

ENV PORT 80
EXPOSE 80

CMD ["node", "server.js"]
