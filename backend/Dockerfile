FROM node:alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 8000

# run with nodemon, you can check in 'package/json'
CMD ["npm", "run", "start"]