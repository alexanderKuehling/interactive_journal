# interactive_journal
`
git clone https://github.com/alexanderKuehling/interactive_journal.git 
'

Initialize Project on linux instance
`
sudo mkdir -p /var/www/audio
sudo cp {your_git_path}/interactive_journal/index.html /var/www/audio/index.html
`

## Nginx vorbereiten 
`
sudo apt update
sudo apt install nginx -y
sudo nano /etc/nginx/sites-available/audio
`

`
server {
    listen 80;
    server_name audio.example.com;

    root /var/www/audio;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}

`
Start ngingx
`
sudo ln -s /etc/nginx/sites-available/audio /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx

`