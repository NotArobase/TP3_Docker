FROM node:18

# Create app directory

WORKDIR /src/app

COPY . .

RUN npm install

RUN npm link --local todo-list-client

RUN npm run build

CMD ["start"]

EXPOSE 3006