# Stage 1: Build the application
FROM node:18 AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build  # Replace with your build command if necessary

# Stage 2: Create the final lightweight image
FROM node:18-slim

WORKDIR /app
COPY --from=builder /app .  
EXPOSE 3000  

CMD [ "npm", "start" ]  
