# Using Docker Compose to Deploy LiteLLM

## Introduction

Just a simple way to deploy LiteLLM with Docker Compose.

## How to Use

Install Docker and Docker Compose, then run the following command:

```bash
docker-compose up -d
```

Then you can access LiteLLM at `http://localhost:4000`.

## Common Issues and Solutions

### Creating New LiteLLM Users
If you encounter authentication issues when first using admin login (e.g., `Authentication Error, User not found`), you can manually create a new user using the following method:

```bash
curl --location 'http://localhost:4000/user/new' \
--header 'Authorization: Bearer YOUR_MASTER_KEY' \
--header 'Content-Type: application/json' \
--data-raw '{"user_email": "admin@example.com", "user_id": "admin"}'
```

Note: This issue may only exist in specific versions of Docker images (such as v1.63.8-stable) and might be fixed in future versions.
