# Docker Node App Task


1. Create a Dockerfile for app:
-
```
FROM node:6
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "app.js"]
```

2. Create docker-compose.yml file which defines app and database and build containers.
- example:
```
app:
    container_name: app
    build: ./app
    environment:
      - DB_HOST=mongodb://mongo:27017/posts
    ports:
      - "3000:3000"
    volumes:
      - ./app/data:/data
    depends_on: 
      - mongo
 ```
3. Use command to run and build it:
```
docker-compose up --build
```




