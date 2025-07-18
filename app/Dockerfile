FROM node:18-slim

# Update zlib
RUN apt-get update \
    && apt-get install -y zlib1g-dev \
    && apt-get upgrade -y zlib1g \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000
CMD ["node", "src/index.js"]
