# OpenVPN Admin

## Summary
Administrate its OpenVPN with a web interface (logs visualisations, users managing...) and a SQL database.

![Previsualisation configuration](https://lutim.cpy.re/fUq2rxqz)
![Previsualisation administration](https://lutim.cpy.re/wwYMkHcM)


## Prerequisite

  * GNU/Linux with Bash and root access
  * Fresh install of OpenVPN
  * Web server (NGinx, Apache...)
  * MySQL
  * PHP >= 5.5 with modules:
    * zip
    * pdo_mysql
  * bower
  * unzip
  * wget
  * sed
  * curl

### Arch Linux 

````
# pacman -S bower php mariadb openvpn php-fpm net-tools nginx
# mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
# systemctl enable mariadb
# systemctl start mariadb
# mysql_secure_installation
# systemctl enable php-fpm.service
# systemctl start php-fpm.service
```
Enable PHP Extensions: `mysqli pdo_mysql zip`

## Tests

Only tested on Arch Linu. Feel free to open issues.

## Installation

  * Setup OpenVPN and the web application:

        $ git clone  https://github.com/C0D3D3V/OpenVPN-Admin.git
        $ cd OpenVPN-Admin
        # ./install.sh /usr/share/nginx/vpn http http

  * Setup the web server (Apache, NGinx...) to serve the web application.
  * Create the admin of the web application by visiting `http://your-installation/index.php?installation`

## Usage

  * Start OpenVPN on the server (for example `systemctl start openvpn-server@server`)
  * Connect to the web application as an admin
  * Create an user
  * User get the configurations files via the web application (and put them in */etc/openvpn*)
  * Users on GNU/Linux systems, run `chmod +x /etc/openvpn/update-resolv.sh` as root
  * User run OpenVPN (for example `systemctl start openvpn@client`)

## Update

    $ git pull origin master
    # ./update.sh /var/www

## Desinstall
It will remove all installed components (OpenVPN keys and configurations, the web application, iptables rules...).

    # ./desinstall.sh /var/www

## Use of

  * [Bootstrap](https://github.com/twbs/bootstrap)
  * [Bootstrap Table](http://bootstrap-table.wenzhixin.net.cn/)
  * [Bootstrap Datepicker](https://github.com/eternicode/bootstrap-datepicker)
  * [JQuery](https://jquery.com/)
  * [X-editable](https://github.com/vitalets/x-editable)
