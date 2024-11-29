#Instalar o numlockx
sudo apt install numlockx

#Editar o arquivo
/etc/lightdm/lightdm.conf
## procurar a linha [Seat:*] e acrescentar o comando abaixo
[Seat:*]
greeter-setup-script=/usr/bin/numlockx on