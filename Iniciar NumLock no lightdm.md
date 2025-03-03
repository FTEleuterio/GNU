#Instalar o numlockx
sudo apt install numlockx

XFCE
#Editar o arquivo
/etc/lightdm/lightdm.conf
## procurar a linha [Seat:*] e acrescentar o comando abaixo
[Seat:*]
greeter-setup-script=/usr/bin/numlockx on


KDE
#Editar ou criar o arquivo
/etc/sddm.conf
## inserir alinha
Numlock=on

Nas configurações do Teclado Ligar
