# DecapBridge Self-Hosted Examples

Docker Compose examples for self-hosting DecapBridge.

See more information regarding Self-Hosting in the docs on the website [here](https://decapbridge.com/docs/self-hosting).

## Prerequisites

For testing (simple setup):

- Docker and Docker Compose

For production (realistic setup):

- A domain name with 3 subdomains pointed to your server
- A reverse proxy with SSL (Nginx, Traefik, Caddy, etc.)
- Optional: SMTP server or Mailgun API key (for email notifications, invite links can also be copied from the UI)
- Optional: SSO credentials (Google, Microsoft)

## Examples

| Example                                                            | Description                                                       |
| ------------------------------------------------------------------ | ----------------------------------------------------------------- |
| [`docker-compose-simple.yml`](./docker-compose-simple.yml)         | Minimal setup: no email, no SSO — works as-is locally for testing |
| [`docker-compose-production.yml`](./docker-compose-production.yml) | Full setup: with Mailgun email and Google/Microsoft SSO           |

## Getting started

Spin up the example docker-compose files:

```bash
docker compose -f docker-compose-simple.yml up
```

This should work locally. For production, you will need to review and fill the environment variables, then point your reverse proxy to the exposed ports:

| Service     | Port |
| ----------- | ---- |
| Web UI      | 8080 |
| Auth API    | 8055 |
| Git Gateway | 8081 |

Once the docker stack is up and running, navigate to the UI page in your browser (http://localhost:8080 if using the simple example), then create a first user and register your first site.

## Notes

- A commercial self-hosting license is required for commercial use. See [decapbridge.com](https://decapbridge.com) for details.
