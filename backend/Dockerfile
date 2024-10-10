# Use Node.js base image
FROM node:14

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./
RUN npm install --only=production

# Copy app source
COPY . .

# Expose backend port
EXPOSE 5000

# Start backend application
CMD [ "npm", "start" ]
