# 🌱 Environment Variables

The following table describes the environment variables that alter the behavior of APPS PLAID. These valeus will vary by environment

| Variable            | Purpose                                                    |
|:--------------------|:-----------------------------------------------------------|
| `PLAID_IMAGE_OWNER` | Set to blank to use a local `plaid` Docker image           |
| `PLAID_VERSION`     | Set to a version tag, such as `latest`                     |
| `PLAID_PORT`        | Set to the TCP port number where APPS PLAID listens        |
| `DB_USER`           | Database username                                          |
| `DB_PASSWORD`       | Password for the database username                         |
| `DB_DATABASE`       | Name of the database                                       |
| `DB_HOST`           | Host where the database is accessed                        |
| `SMTP_HOST`         | Host where the SMTP server is accessed                     |
| `SMTP_PORT`         | Port number where the SMTP server listens                  |
| `SMTP_DOMAIN`       | Domain to use when generating emails                       |
| `SMTP_SECURITY`     | SMTP encryption to use; either `TLS`, `STARTTLS`, or blank |
| `SMTP_USER`         | Username if SMTP server requires authentication            |
| `SMTP_PASSWORD`     | Password if SMTP server requires authentication            |

When running `docker compose`, these variables may be set in the host shell (such as with `export` or `setenv`), using the `/usr/bin/env` command, or in an environment file (which `docker compose` reads if specified with `--env-file`). However, putting sensitive credentials such as `SMTP_PASSWORD` in such a file may be risky. Protect such a file carefully.

**👉 Note:** using `/usr/bin/env SMTP_PASSWORD=1234 docker compose …` is also risky, since command-line arguments may be read by any other process on the system.
