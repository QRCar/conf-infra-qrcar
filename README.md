# Nginx for QRCar
> cbarange | 18th November 2020
---

## Get Started

```bash
sudo ln nginx_qrcar.conf /etc/nginx/sites-enabled/
sudo snap install core; sudo snap refresh core
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot
# Use sand box
sudo certbot certonly --manual --cert-name cbarange -d *.qrcar.cbarange.ovh --register-unsafely-without-email --dry-run
# When ready generated certificat
sudo certbot certonly --manual --cert-name cbarange -d *.qrcar.cbarange.ovh --register-unsafely-without-email
```

## Postgres
```bash
sudo docker run --rm -it --name postgresql \
-v /app/IA_Workshop/postgres/data:/var/lib/postgresql/data \
-e POSTGRES_PASSWORD=patate -p 5432:5432 postgres
```

## Phoenix

```bash
wget -O- https://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc | sudo apt-key add -
echo "deb https://packages.erlang-solutions.com/ubuntu focal contrib" | sudo tee /etc/apt/sources.list.d/rabbitmq.list
sudo apt update
sudo apt install erlang
erl

sudo apt-get update
sudo apt-get install -y inotify-tools

sudo apt-get install elixir
elixir -v
mix local.hex
mix archive.install hex phx_new 1.5.1
```
