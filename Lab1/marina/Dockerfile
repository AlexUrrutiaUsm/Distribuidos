FROM golang:1.24.2
WORKDIR /app
COPY . /app
RUN go mod download
ENV RABBITMQ_HOST=rabbitmq
ENV RABBITMQ_PORT=5672
EXPOSE 50052
# Explicitly change directory and build in a single command
RUN cd marina && go build -o marina .
# Set working directory for CMD execution
WORKDIR /app/marina
CMD ["sh", "-c", "./marina -rabbitmq_host=$RABBITMQ_HOST -rabbitmq_port=$RABBITMQ_PORT"]
