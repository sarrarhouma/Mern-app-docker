# Use Node.js Alpine image for a lightweight build
FROM node:lts-alpine

# Set working directory inside the container
WORKDIR /app

# Copy only package.json and package-lock.json first to leverage Docker's caching
COPY package*.json ./

# Install dependencies using npm
RUN npm install 

# Copy the rest of the application files
COPY . .

# Build the React application
#RUN npm run build

# Install the "serve" package locally, avoiding global installation
#RUN npm install serve 

# Expose the port that the app will run on
EXPOSE 3000

# Use "npx" to serve the build folder without requiring global installations
#CMD ["npx", "serve", "-s", "build", "-l", "3000"]
CMD [ "npm","start" ]
