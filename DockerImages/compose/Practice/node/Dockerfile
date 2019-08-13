FROM ubuntu

RUN apt-get update
RUN apt-get install --yes nodejs
RUN apt-get install --yes npm

RUN node -v

RUN npm i -g nodemon

RUN mkdir /var/nodejs

RUN npm -v && \
    nodemon -v

COPY nodecode /var/nodejs

WORKDIR /var/nodejs

RUN npm install

EXPOSE 3000

CMD ["nodemon", "index.js"] 


