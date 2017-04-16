# HAProxy

https://raw.githubusercontent.com/Luismcplopes/HAProxy/master/img/haproxystats.jpg
https://raw.githubusercontent.com/Luismcplopes/HAProxy/master/img/haproxy.jpg

* Instalar e configurar WebServers1 
* Instalar e configurar WebServers2
* Instalar e configurar HAProxy
* Testar


# - Configuração do (WebServers1) e virtualhost test.dev
sudo apt-get update && sudo apt-get upgrade -y

## -Instalar apache2
sudo apt-get install apache2 -y

### -Criar directório test.dev
sudo mkdir /var/www/html/test.dev

### -Definir permissões
sudo chown -R $USER:$USER /var/www/html/test.dev && sudo chmod -R 755 /var/www

### -Criar index.html
sudo vim /var/www/html/test.dev/index.html

### -Criar um VirtualHost que aponte para test.dev
sudo nano /etc/apache2/sites-available/test.dev.conf

## Restart no apache2
sudo apache2ctl configtest
sudo a2ensite test.dev.conf
 /etc/init.d/apache2 restart
 
 
#  Configuração do (webservers2) e virtualhost test.dev
sudo apt-get update && sudo apt-get upgrade -y

## -Instalar apache2
sudo apt-get install apache2 -y

### -Criar directório test.dev
sudo mkdir /var/www/html/test.dev

### -Definir permissões
sudo chown -R $USER:$USER /var/www/html/test.dev && sudo chmod -R 755 /var/www

### -Criar index.html
sudo vim /var/www/html/test.dev/index.html

### -Criar um VirtualHost que aponte para test.dev
sudo nano /etc/apache2/sites-available/test.dev.conf

## Restart no apache2
sudo apache2ctl configtest
sudo a2ensite test.dev.conf
 /etc/init.d/apache2 restart


# -Instalar HAProxy
```
sudo apt-get update && sudo apt-get upgrade -y
```
```
sudo apt-get install haproxy
```

## -Configurar HAProxy

### -Adicionar ao ficheiro /etc/default/haproxy a linha:
ENABLED=1 


### -Ficheiro de configuração:
```
sudo cp /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg_bck
```
```
sudo rm /etc/haproxy/haproxy.cfg && sudo vim /etc/haproxy/haproxy.cfg
```


## - Restart ao serviço
```
sudo service haproxy restart
```


# Testar
## Teste Haproxy
    http://192.168.1.9/test.dev/
    
## webserver1
    http://192.168.1.6/test.dev/
    
## webserver2
    http://192.168.1.10/test.dev/

## Estatisticas
    admin:admin
    http://192.168.1.9/haproxy?stats







