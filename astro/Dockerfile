# Use Node.js as the base image
FROM node:18

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package files for dependency installation
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application
COPY . .

# Build the Astro site for production
RUN npm run build

# Expose the port Astro uses
EXPOSE 3000

# Default command to serve the site
CMD ["npm", "run", "preview"]
