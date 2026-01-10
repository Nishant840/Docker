FROM node:20

WORKDIR /app

# since package doesn't change often so it's better to cached it
COPY package* .
COPY ./prisma .

RUN npm install
RUN npx prisma generate

COPY . .
RUN npm run build
EXPOSE 3000

CMD ["node", "dist/index.js"]