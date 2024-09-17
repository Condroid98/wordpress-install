# wordpress-install
Instal Apache, MySQL, dan PHP dengan perintah berikut
```
sudo apt-get update
sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql -y
```
download dan pasang wordpress
```
wget https://wordpress.org/latest.tar.gz
tar xzvf latest.tar.gz
sudo cp -r wordpress/* /var/www/html/
```
Atur Izin dan konfigurasi Apache2
```
sudo chown -R www-data:www-data /var/www/html/
sudo chmod -R 755 /var/www/html/
sudo nano /etc/apache2/sites-available/000-default.conf
```
Restart Apache
```
sudo systemctl restart apache2
```
buat database wordpressnya
*ubahlah user dan password
```
sudo mysql
CREATE DATABASE wordpress;
GRANT ALL PRIVILEGES ON wordpress.* TO 'user'@'localhost' IDENTIFIED BY 'password';
FLUSH PRIVILEGES;
EXIT;
```
akses 127.0.0.1 atau localhost

