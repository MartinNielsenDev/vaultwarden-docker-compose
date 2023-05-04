## Get [vaultwarden](https://github.com/dani-garcia/vaultwarden) up and running with docker-compose immdiately.

## Requirements

- A `domain.tld` pointing to the server you plan to host vaultwarden on.
- HTTPs configured & enabled. (vaultwarden will not allow you to login without it)

## Enable HTTPs (optional)

- Install [certbot](https://certbot.eff.org/)
- Run `certbot --nginx` OR `certbot certonly --manual`
- The files will be located in `/etc/letsencrypt/live/domain.tld/`

## Usage

1. Clone the repo (`git clone https://github.com/MartinNielsenDev/vaultwarden-docker-compose.git`)
2. Edit the configuration file `.env`
3. Run `docker-compose up -d`

## Configuration (.env)

| Variable                                                                           | Description                               | Example                                                                                                                                                                                                                                                                                                          |
|------------------------------------------------------------------------------------|-------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DOMAIN                                                                             | Domain you want to access vaultwarden at  | vault.domain.com                                                                                                                                                                                                                                                                                                 |
| DATABASE_URL                                                                       | Database config                           | sqlite:///db.sqlite3<br/>[mysql://[[user]:[password]@]host[:port][/database]](https://github.com/dani-garcia/vaultwarden/wiki/Using-the-MariaDB-%28MySQL%29-Backend)<br/>[postgresql://[[user]:[password]@]host[:port][/database]](https://github.com/dani-garcia/vaultwarden/wiki/Using-the-PostgreSQL-Backend) |
| [SMTP_HOST](https://github.com/dani-garcia/vaultwarden/wiki/SMTP-Configuration)    | The SMTP host                             | smtp.domain.com                                                                                                                                                                                                                                                                                                  |
| SMTP_FROM                                                                          | From email address                        | noreply@domain.com                                                                                                                                                                                                                                                                                               |
| SMTP_USERNAME                                                                      | SMTP server credential                    |                                                                                                                                                                                                                                                                                                                  |
| SMTP_PASSWORD                                                                      | SMTP server credential                    |                                                                                                                                                                                                                                                                                                                  |
| SMTP_PORT                                                                          | SMTP server config                        | 587                                                                                                                                                                                                                                                                                                              |
| SMTP_SECURITY                                                                      | SMTP server config                        | starttls                                                                                                                                                                                                                                                                                                         |
| [ADMIN_TOKEN](https://github.com/dani-garcia/vaultwarden/wiki/Enabling-admin-page) | Password to access vault.domain.com/admin |                                                                                                                                                                                                                                                                                                                  |

Once the container is up and running, you can access vaultwarden at the domain set in `.env` (e.g `https://vaultwarden.domain.tld`)

## Tested on

- Amazon Linux 2023
- Amazon Linux 2
- Ubuntu 22.04
- Windows 11
