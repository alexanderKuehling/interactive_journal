# interactive_journal
`
git clone https://github.com/alexanderKuehling/interactive_journal.git 
'

Initialize Project on linux instance
`
sudo mkdir -p /var/www/audio
sudo cp {your_git_path}/interactive_journal/index.html /var/www/audio/index.html
`

## prepare Nginx  
`
sudo apt update
sudo apt install nginx -y
sudo nano /etc/nginx/sites-available/audio
`
Config is in file ngingx_config. Replace the the placeholders.
Start ngingx
`
sudo ln -s /etc/nginx/sites-available/audio /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx

`
## HTTPS
`
sudo apt install certbot python3-certbot-nginx -y
sudo certbot --nginx -d mnemo.example.com

sudo certbot --nginx -d n8n.your-domain.com
`

## Docker
Start docker with compose.yaml
`
docker compose up -d 
`
## Setup workflow
Create an n8n account in the webinterface

Replace the placeholders in the mnemo_audio.json and import the json in the webinterface of n8n into an workflow and publish it
