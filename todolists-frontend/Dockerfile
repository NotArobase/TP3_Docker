FROM node:18

# Create app directory
WORKDIR /src/app

COPY ./package*.json ./

# Install yalc globally
RUN npm install -g yalc

# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Link the shared package using yalc
RUN yalc add todo-lists

# Build the application
RUN npm run build

# Set default command
CMD ["npm", "start"]

EXPOSE 3006
