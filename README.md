# run web expo

```
apt-get update && apt-get upgrade
```


https://github.com/nodesource/distributions/blob/master/README.md

node js install
```
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\
sudo apt-get install -y nodejs
```
```
apt-get install npm
```
konfigurasi ip vps ke domain memngunakan nginx

install nginx
```
apt install nginx
```

service command line

```
sudo nginx -t
```
```
sudo service nginx restart
```
```
sudo service nginx status
```


jika semua ok kita konfigurasi


```
cd /etc/nginx/conf.d
```

nano namadomainkamu.conf

example
```
nano managementexpo.web.id.conf
```

isi bagian ini
```
server {
   listen 80;
   server_name managementexpo.web.id www.managementexpo.web.id;

   location / {
      proxy_pass http://localhost:5173;
      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Host $host;
      proxy_set_header Connection 'upgrade';
      proxy_cache_bypass $http_upgrade;
   }
}  
```

aktifkan port
```
ufw enable
```
```
ufw allow 22
ufw allow OpenSSH
ufw allow 5173
ufw allow 'Nginx HTTP'
```

cek status ufw

```
ufw status
```

git clone project

```
git clone https://github.com/andixfaizan/sayangwe.git
```

masuk screen

```
screen -S sayangwe
```
```
cd sayangwe
```
```
npm install
```
```
npm run build
```
```
npm run dev
```

Done
