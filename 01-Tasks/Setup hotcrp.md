---
type: "[[Task]]"
expected_hours: 12
actual_hours: 7
start_date: 2026-10-12
end_date:
---
**Result**:
- Deployed hotcrp in a test env
- Deploy hotcrp in prod
- Write documentaion on how to deploy it

# Execution log:
#### 2026.10.12.
- `2.2h`:
	- docker build failed - i had to update base image of `./docker/php/Dockerfile` to `php:8.2-fpm-bookworm`
	- starting container fails - see "php-addr-error"
	- replace `nginx:9000` with `9000` from `docker/php/www.conf`
	- can't connect to the server - `Error Code: SSL_ERROR_RX_RECORD_TOO_LONG`
	- replace `ports: - 9001:80` with `expose "80"`
	- create new subdomain for hotrcp
	- setup reverse proxy
	- start setting up mailserver
- `2.5`:
	- setup mailserver
	- setup `anubis`

#### 2026.10.13.
- `1.2h`:
	- give admin privileges to other ADG foundation member
	- play around with the website
	- figure out how to make backup
#### 2026.10.14.
- `0.3h` - look for payment option and write a ticket about it
#### 2026.10.29.
- `2.5h` - Deploy HotCRP on prod server with [Zoltán Kovács](Zoltán%20Kovács)
- `3.3h` - start working on documentation
- `2.2h` - finish documentation, follow steps on my vps to validate them

---
php-addr-error:
```
php-1    | [12-Oct-2026 08:07:07] ERROR: unable to bind listening socket for address 'nginx:9000': Cannot assign requested address (99)
php-1    | [12-Oct-2026 08:07:07] ERROR: unable to bind listening socket for address 'nginx:9000': Cannot assign requested address (99)
php-1    | [12-Oct-2026 08:07:07] ERROR: FPM initialization failed
php-1    | [12-Oct-2026 08:07:07] ERROR: FPM initialization failed
php-1 exited with code 78 (restarting)
```