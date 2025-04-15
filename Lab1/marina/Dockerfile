FROM golang:1.24.2
WORKDIR /app
COPY . /app
RUN go mod download
WORKDIR /app/marina
ENV RABBITMQ_HOST=rabbitmq
ENV RABBITMQ_PORT=5672
EXPOSE 50052
RUN go build -o marina .
CMD ["sh", "-c", "./marina -rabbitmq_host=$RABBITMQ_HOST -rabbitmq_port=$RABBITMQ_PORT"]
