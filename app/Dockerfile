# Stage 1: Build
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install

# Stage 2: Production
FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app /app
COPY . .
EXPOSE 3000
CMD ["node", "server.js"]  # Replace with your app entry point
