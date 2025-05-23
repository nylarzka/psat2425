# Penilaian Sumatif Akhir Tahun
## Mapil DevOps XI TJKT 1 - Penilaian Praktek
### SMKN 1 Banyumas - TA. 2024 2025


#
# Cara mendeploy Aplikasi

## 1. Buat File .env

```.env
DB_USER=....  (isi dengan user RDS)
DB_PASS=....  (isi dengan password RDS)
DB_NAME=....  (isi dengan nama database yang akan dibuat di RDS)
DB_HOST=....  (isi dengan Endpoint RDS)
```

contoh:

```.env
DB_USER=admin
DB_PASS=P4ssw0rd123
DB_NAME=psat2425
DB_HOST=rdsku.czt6n8ylfvyb.us-east-1.rds.amazonaws.com

```
# Perintah untuk Deploy
sudo apt update -y

sudo apt install -y apache2 php php-mysql libapache2-mod-php mysql-client

sudo rm -rf /var/www/html/{*,.*}

sudo git clone [alamat github yang akan diclone] /var/www/html

sudo chmod -R 777 /var/www/html

echo DB_USER=[username rds/database] > /var/www/html/.env
echo DB_PASS=[password rds/databse]  >> /var/www/html/.env
echo DB_NAME=[name rds/database]  >> /var/www/html/.env
echo DB_HOST=[endpoint rds/database] >> /var/www/html/.env

sudo apt install openssl
sudo a2enmod ssl
sudo a2ensite default-ssl.conf
sudo systemctl reload apache2

# Perintah untuk Deploy otomatis .sh
#!/bin/bash
echo '#!/bin/bash
sudo apt update -y
sudo apt install -y apache2 php php-mysql libapache2-mod-php mysql-client
sudo rm -rf /var/www/html/{,.}
sudo git clone [repository githubmu] /var/www/html
sudo chmod -R 777 /var/www/html
echo DB_USER=[username rds] > /var/www/html/.env
echo DB_PASS=[password rds]  >> /var/www/html/.env
echo DB_NAME=[nama database]  >> /var/www/html/.env
echo DB_HOST=[endpoint rds] >> /var/www/html/.env
sudo apt install -y openssl
sudo a2enmod ssl
sudo a2ensite default-ssl.conf
sudo systemctl reload apache2' > /home/ubuntu/otomatis.sh

chmod +x /home/ubuntu/otomatis.sh  

## 2. Jalankan 
Jalankan dengan username dan password default berikut ini
#
### username = admin
### password = 123
#

Kemudian inputkanlah data sesuai dengan datamu
SELAMAT MENCOBA YA TEMAN-TEMAN! JANGAN LUPA UNTUK SELALU BERDOA SEBELUM MEMULAI KEGIATAN.
