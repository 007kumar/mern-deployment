FROM node:16

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm set fetch-retry-mintimeout 20000 && npm set fetch-retry-maxtimeout 120000

# Set a reliable npm registry
RUN npm config set registry https://registry.npmmirror.com/

# Install dependencies with better stability
RUN npm install --legacy-peer-deps --silent

COPY . .

EXPOSE 5000

CMD ["npm", "start"]

