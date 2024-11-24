# Use the official Node.js image
FROM node:18

# Set the working directory
WORKDIR /usr/src/app

# Clone the Git repository
# Replace <your-repo-url> with your repository URL
RUN apt-get update && apt-get install -y git && \
    git clone https://github.com/premedios/personalsite-astro.git . && \
    rm -rf .git  # Optional: Remove the .git directory to reduce image size

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy the application files
COPY . .

# Build the project
RUN npm run build

# Expose the port Astro runs on
EXPOSE 3000

# Run the built project
CMD ["npm", "run", "dev"]
