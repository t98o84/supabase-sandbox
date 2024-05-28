# Supabase sandbox

## Accesses

| Service    | URL                                                     |
|------------|---------------------------------------------------------|
| WEB        | http://localhost:3000                                   |
| API        | http://127.0.0.1:54321                                  |
| GraphQL    | http://127.0.0.1:54321/graphql/v1                       |
| S3 Storage | http://127.0.0.1:54321/storage/v1/s3                    |
| DB         | postgresql://postgres:postgres@127.0.0.1:54322/postgres |
| Studio     | http://127.0.0.1:54323                                  |
| Inbucket   | http://127.0.0.1:54324                                  |

## Installation

1. Clone the repository
2. Install the dependencies
    ```bash
    docker compose run --rm web npm install
    ```
3. Copy .env.example to .env
    ```bash
    cp .env.example .env
    ```
4. Set the project root environment variable.
   ```bash
   echo "PROJECT_ROOT=$(pwd)" >> .env
   ```
5. Start the supabase server
   ※ Do not use the -d option as it uses the start-up log
   ```bash
   docker compose up supabase
   ```
6. Set the environment variables in the .env file
    ```bash
    NEXT_PUBLIC_SUPABASE_ANON_KEY=anon key
    ```
7. Start the web server
    ```bash
    docker compose up -d web
    ```
8. Access the web server
    - http://localhost:3000

## Stop the server

```bash
docker compose stop
docker compose run --rm supabase npx supabase stop
```
