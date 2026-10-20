FROM node:14-alpine
# npm 6 (bundled with Node 14) ignores lockfileVersion 3; npm 8 honors it and still supports Node 14
RUN npm install -g npm@8 && npm install -g @angular/cli@12
WORKDIR /opt/app
COPY app/package*.json ./
RUN npm ci
COPY app/ ./
EXPOSE 4200
CMD ["ng", "serve", "--host", "0.0.0.0", "--disable-host-check"]
