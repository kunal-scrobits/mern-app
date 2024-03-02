# Base image
FROM node:18.16.0-alpine

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./
RUN yarn

# Bundle app source
COPY . .

# Build the app
RUN yarn build

# Install serve and serve the build directory
RUN yarn add global serve

EXPOSE 3000

CMD ["npx", "serve", "-s", "build", "-l", "3000"]
