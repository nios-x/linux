# Stage 1
FROM node:lts-alpine3.24 AS builder
WORKDIR /app
COPY . .
RUN npm i


# Stage 2
FROM gcr.io/distroless/nodejs24-debian13
WORKDIR /app
COPY --from=builder /app /app
EXPOSE 3000
CMD ["index.js"]