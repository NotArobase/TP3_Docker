FROM node:18

# Create app directory
WORKDIR /app

COPY ./package*.json ./
# Install dependencies
RUN npm install

# Install yalc globally
RUN npm install -g yalc

# Publish the shared package first
RUN yalc publish

# Copy the rest of the application files
COPY . .

# Install Fastify CLI globally
RUN npm install -g fastify-cli

# Build the TypeScript project
RUN npm run build:ts

# Set default command
CMD ["fastify", "start", "-l", "info", "dist/app.js"]

EXPOSE 3000
