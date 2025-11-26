#Build Stage
FROM node:18-alpine AS build

WORKDIR /usr/src/app

COPY package.json package-lock.json ./

RUN npm ci --omit=dev

COPY . .

#Production Stage
FROM node:18-alpine

WORKDIR /usr/src/app

COPY --from=build /usr/src/app /usr/src/app

CMD ["npm", "start"]
