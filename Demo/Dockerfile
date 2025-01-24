# Stage 1: Build
FROM node:18 AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# Stage 2: Distroless Runtime
FROM gcr.io/distroless/nodejs18

WORKDIR /app
COPY --from=builder /app /app

EXPOSE 8080
CMD ["app.js"]
