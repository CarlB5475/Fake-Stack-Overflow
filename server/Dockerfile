FROM node:20.12.0

WORKDIR /server_app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 8000 

CMD ["npm", "start"]