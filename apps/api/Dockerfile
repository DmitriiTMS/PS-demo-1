FROM node:24-alpine AS build
WORKDIR /opt/app
ADD *.json ./
RUN npm install --legacy-peer-deps
ADD . .
RUN npm run build api

FROM node:24-alpine
WORKDIR /opt/app
ADD package.json ./
RUN npm install --only=prod --legacy-peer-deps
COPY --from=build /opt/app/dist/apps/api ./dist
CMD ["node", "dist/main.js"]