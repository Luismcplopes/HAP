# -Instalar HAProxy
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install haproxy

## -Configurar HAProxy

### -Adicionar ao ficheiro /etc/default/haproxy a linha:
ENABLED=1 


### -Ficheiro de configuração:
sudo cp /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg_bck
sudo rm /etc/haproxy/haproxy.cfg && sudo vim /etc/haproxy/haproxy.cfg


## - Restart ao serviço
sudo service haproxy restart
