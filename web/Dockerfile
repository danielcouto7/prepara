FROM node:4

ENV HOME=/app

RUN mkdir $HOME

WORKDIR $HOME

COPY ./src $HOME

RUN npm install -g bower gulp sequelize-cli pg

RUN chown -R 1001:1001 .
RUN chmod -R 755 .
USER 1001

RUN npm install && bower install

VOLUME /app/server
VOLUME /app/app
VOLUME /app/test
VOLUME /app/public
VOLUME /app/node_modules

EXPOSE 8000
EXPOSE 35729
CMD ["npm", "start"]