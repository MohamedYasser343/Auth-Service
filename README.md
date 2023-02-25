# Auth-Service
complex authentication service using rust

### Usage

```bash

# SQLX CLI
cargo install --git https://github.com/launchbadge/sqlx sqlx-cli

# Download the repo
git clone https://github.com/MohamedYasser343/Auth-Service.git


# Run migrations
sqlx mig run

# Run the server (http://<host>:<port>)
cargo run

```

### API
- Health endpoint: `GET` /
  ```
  curl http://<host>:<port>/
  ```
- User Signup: `POST` /signup
  ```
  curl --request POST \
    --url http://<host>:<port>/signup \
    --header 'content-type: application/json' \
    --data '{
        "username": "user1",
        "email": "user1@example.com",
        "password": "user1"
    }'
  ```
- Auth: `POST` /auth
  ```
  curl --request POST \
    --url http://<host>:<port>/auth \
    --user user1
  ```
- User profile: `GET` /me
  ```
  curl --request GET \
  --url http://<host>:<port>/me \
  --header 'authorization: Bearer <jwt_token>'
  ```
- Update profile: `PUT` /me
  ```
  curl --request POST \
    --url http://<host>:<port>/me \
    --header 'authorization: Bearer <jwt_token>' \
    --header 'content-type: application/json' \
    --data '{
        "full_name": "User One"
    }'
  ```
- Example jwt token (debug it in [JWT.io](https://jwt.io/))
