FROM node:18-alpine
WORKDIR /app
# RUN npm install -g yarn

COPY package.json .
RUN yarn install

# Install yarn
COPY . .


# Expose the necessary ports
EXPOSE 3000
CMD ["yarn", "start"]
