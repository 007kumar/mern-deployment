# Use Node.js 16 LTS as base image
FROM node:16

# Set working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json first to leverage Docker caching
COPY package*.json ./

# Install dependencies
RUN npm install --legacy-peer-deps --silent

# Copy the entire project to the working directory
COPY . .

# Expose port 3000
EXPOSE 3001

# Use a non-root user for better security
RUN useradd --create-home appuser
USER appuser

# Start the application
CMD ["npm", "start"]

