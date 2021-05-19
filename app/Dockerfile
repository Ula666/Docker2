

# Dockerfile for Nodejs app
FROM node:6
# setting up the working dir inside the container

WORKDIR /usr/src/app
# COPY everything or dependencies required
COPY package*.json ./
#COPY app/
# run npm install after we have copied the depencies
RUN npm install
COPY . .
# EXPOSE THE PORT FOR OUR APP
EXPOSE 3000
# launch the app
CMD ["node", "app.js"]

