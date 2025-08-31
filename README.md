````markdown
# go-redis-helper-kit

A lightweight Go helper package for working with Redis.  
Provides easy connection management and CRUD helpers for Redis operations.

---

## Installation

```bash
go get github.com/abhishekprakash256/go-redis-helper-kit
````

---

## Configuration

Database connection settings can be configured in your Go code (or a config file).
Example in `config/config.go`:

```go

type DBConfig struct {
	Host     string
	Port     int
}
```

Example YAML-based config (optional):

```yaml
redis:
  host: "localhost"
  port: 6379
  password: ""
  db: 0
```

The `examples/main.go` shows how to read this config and initialize a Redis client.

---

## Running Redis with Docker

Start a Redis container:

```bash
docker run -d --name redis \
  --network my_network \
  -p 6379:6379 \
  redis:latest
```

Verify Redis is running:

```bash
docker ps
```

Connect to Redis CLI:

```bash
docker exec -it redis redis-cli
```



## Project Structure

```
.
├── config
│   └── config.go               # Redis configuration struct
├── examples
│   └── main.go                 # Example usage of the helper kit
├── redis
│   └── db
│       ├── connection
│       │   └── redis_connector.go  # Redis client initialization
│       └── crud
│           └── redis_crud.go       # CRUD helper functions
├── go.mod
├── go.sum
├── README.md
└── steps.txt
```

