FROM golang:1.21-alpine
WORKDIR /app

# Installer glibc
RUN apk add --no-cache libc6-compat

# Copier le projet et compiler
COPY . .
RUN go build -o main .

# Exposer le port et lancer l'application
EXPOSE 8081
CMD ["./main"]
