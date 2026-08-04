# /biolink-backend/Dockerfile

# Step 1: Use a Debian-based slim image to support AI native C++ binaries
FROM node:20-slim

# Step 2: Install OpenSSL (Debian syntax)
RUN apt-get update && apt-get install -y openssl

# Step 3: Set the working directory inside the container
WORKDIR /app

# (Leave the rest of the file exactly the same!)
COPY package*.json ./
RUN npm install
COPY . .
RUN DATABASE_URL="postgresql://dummy:dummy@dummy:5432/dummy" npx prisma generate
RUN npm run build
EXPOSE 5000
CMD ["npm", "start"]