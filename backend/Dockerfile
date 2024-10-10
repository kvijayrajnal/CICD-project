# Use a Node.js base image
FROM node:14

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./
RUN npm install --only=production

# Bundle app source
COPY . .

# Expose frontend port
EXPOSE 3000

# Start the frontend application
CMD [ "npm", "start" ]
