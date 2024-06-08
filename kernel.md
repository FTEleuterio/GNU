**Remover Kernel**
Verificar kernel instalados
dpkg -l | grep linux-image | awk '{print$2}'

sudo apt purge linux-image-x.x.x.x-amd64
sudo apt purge linux-headers-x.x.x.x-amd64