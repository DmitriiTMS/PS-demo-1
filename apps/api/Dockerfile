FROM node:24-alpine
WORKDIR /opt/app
ADD *.json .
RUN npm install
ARG . .
RUN npm run build api
CMD ["node", "dist/apps/api/main.js"]