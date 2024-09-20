Desinstalar Kernel antigo

dpkg -l | grep linux-image | awk '{print$2}'

sudo apt install linux-image-6.10.9-amd64 linux-headers-6.10.9-amd64

Verificar no repositório Kernels disponíveis para atualização

apt search linux-image