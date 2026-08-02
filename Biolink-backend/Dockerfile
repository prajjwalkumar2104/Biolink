# /biocascade-backend/Dockerfile

# Step 1: Use an official lightweight Node.js image
FROM node:20-alpine

# Step 2: Install OpenSSL (Required by Prisma for Alpine Linux)
RUN apk add --no-cache openssl

# Step 3: Set the working directory inside the container
WORKDIR /app

# Step 4: Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Step 5: Copy the rest of the application code
COPY . .

# Step 6: Generate the Prisma client
RUN npx prisma generate

# Step 7: Build the TypeScript code (assuming you have a "build": "tsc" script)
RUN npm run build

# Step 8: Expose the Express API port
EXPOSE 5000

# Step 9: Define the command to start the server
CMD ["npm", "start"]