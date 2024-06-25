**Instalar Kernel**

apt search linux-image
sudo apt install linux-image-4.11.0-1-amd64 linux-headers-4.11.0-1-amd64





**Remover Kernel**
Verificar kernel instalados
dpkg -l | grep linux-image | awk '{print$2}'

sudo apt purge linux-image-x.x.x.x-amd64
sudo apt purge linux-headers-x.x.x.x-amd64