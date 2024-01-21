# Use an official Go runtime as a base image
FROM golang:1.17

# Set the working directory inside the container
WORKDIR /app

# Copy the local package files to the container's workspace
COPY . .

# Use the official Go image as a base image
FROM golang:1.17

# Set the working directory inside the container
WORKDIR /app

# Copy go.mod and go.sum to download dependencies
COPY go.mod go.sum ./

# Download dependencies
RUN go mod download

# Copy the entire project to the working directory
COPY . .

# Build the Go application
RUN go build -o main .

# Expose port 8080 (adjust if necessary)
EXPOSE 8080

# Command to run the application
CMD ["./main"]
