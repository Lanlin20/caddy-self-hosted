# Caddy Self-Hosted with Docker

This repository provides a `docker-compose` setup to run a self-hosted [Caddy](https://caddyserver.com/) reverse proxy.

It is configured to connect to a shared Docker network, allowing easy integration with other services like [n8n](https://github.com/AiratTop/n8n-self-hosted).

## Features

-   Uses the official Caddy Docker image.
-   Automatic HTTPS via Let's Encrypt.
-   Data is persisted in a local volume.
-   Pre-configured for a shared network.
-   Includes scripts for easy management.

## Getting Started

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/AiratTop/caddy-self-hosted.git
    cd caddy-self-hosted
    ```

2.  **Create the shared network:**
    If you haven't already, create the shared Docker network:
    ```bash
    docker network create shared_network
    ```

3.  **Configure environment variables:**
    Open the `.env` file and update the variables with your own settings.

4.  **Start the service:**
    ```bash
    docker compose up -d
    ```

## Usage

-   **Start:** `docker compose up -d`
-   **Stop:** `docker compose down`
-   **Restart:** `./restart-docker.sh`
-   **Update:** `./update-docker.sh` (Pulls the latest Docker image and restarts)

## Connecting with other services

This setup is designed to work with other services on the `shared_network`. To add a new service, add a new block to the `Caddyfile` in the `caddy_config` directory.

## See Also

Check out other self-hosted solutions:

-   [postgresql-self-hosted](https://github.com/AiratTop/postgresql-self-hosted)
-   [mysql-self-hosted](https://github.com/AiratTop/mysql-self-hosted)
-   [clickhouse-self-hosted](https://github.com/AiratTop/clickhouse-self-hosted)
-   [qdrant-self-hosted](https://github.com/AiratTop/qdrant-self-hosted)
-   [n8n-self-hosted](https://github.com/AiratTop/n8n-self-hosted)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author

**Airat Halitov**

- Website: [airat.top](https://airat.top)
- GitHub: [@AiratTop](https://github.com/AiratTop)
- Repository: [caddy-self-hosted](https://github.com/AiratTop/caddy-self-hosted)