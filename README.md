## SettingVirtualHostDebian

```
sudo mkdir -p /var/www/example.com
```
```
sudo chown -R www-data: /var/www/example.com
```
```
nano /etc/apache2/sites-available/example.com.conf
```
```
<VirtualHost *:80>
    ServerName wedding-kami.id
    ServerAlias www.wedding-kami.id
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/weddingkami
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

<Directory /var/www/weddingkami/>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Require all granted

</Directory>

</VirtualHost>
```
```
sudo a2ensite example.com
```
```
sudo a2dissite 000-default.conf
```
```
sudo apachectl configtest
```
```
sudo a2enmod rewrite
```
```
sudo systemctl restart apache2
```
