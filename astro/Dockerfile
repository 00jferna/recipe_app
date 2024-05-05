# syntax=docker/dockerfile:1
FROM node:16-alpine

#setup app dir
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

#change dir
WORKDIR /home/node/app

#copy node json
COPY package*.json ./

#copy project to workdir, changes owner of workdir to user "node"
COPY --chown=node:node . .

#chande to use "node"
USER node

#install node app
RUN npm ci

#expose port for external browser
EXPOSE 3000

#start node app
CMD [ "npm", "start" ]
