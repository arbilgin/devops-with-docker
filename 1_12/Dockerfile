FROM ubuntu

WORKDIR /usr/src/app

RUN apt-get update \
    && apt-get install -y curl ca-certificates \
    && curl -fsSL https://deb.nodesource.com/setup_16.x -o /tmp/nodesource.sh \
    && bash /tmp/nodesource.sh \
    && apt-get install -y nodejs

COPY package*.json ./
RUN npm install

COPY . .

RUN npm run build

EXPOSE 5001

RUN npm install -g serve

CMD ["serve", "-s", "-l", "5001", "build"]