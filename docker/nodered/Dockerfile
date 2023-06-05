FROM nodered/node-red:latest

USER root
RUN adduser node-red dialout

USER node-red

RUN npm install \
    node-red-node-pi-gpiod \
    node-red-dashboard \
    node-red-contrib-influxdb \
    node-red-contrib-home-assistant-websocket \

# copy the settings file
USER node-red
COPY settings.js /usr/src/node-red/.node-red/

# change the startup command to be sure to use our settings.
CMD ["npm", "start", "--", "--userDir", "/data", "--settings", "/usr/src/node-red/.node-red/settings.js"]