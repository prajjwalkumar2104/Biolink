# /biocascade-frontend/Dockerfile

FROM node:20-alpine

WORKDIR /app

# Copy dependency definitions and install
COPY package*.json ./
RUN npm install

# Copy all source files
COPY . .

# Build the Next.js production app
RUN npm run build

EXPOSE 3000

# Start the Next.js production server
CMD ["npm", "start"]