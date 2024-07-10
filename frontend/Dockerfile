# Use the official Node.js image
FROM node:18

# Set the working directory to /app
WORKDIR /app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the application on port 5173
EXPOSE 5173

# Start the application
CMD npm run dev -- --host 0.0.0.0
