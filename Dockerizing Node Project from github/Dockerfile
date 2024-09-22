FROM node

WORKDIR /developer/nodejs/app_from_github

RUN apt-get update && apt-get install -y git 

RUN git clone https://github.com/Kritikamishra-16/Dockerizing_Nodejs_server.git .

ENV port=3000

EXPOSE 3000

RUN npm ci

CMD ["npm", "start"]

