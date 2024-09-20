# Falha Atualização do Kernel Debian Testing
## Erro rrosub-process /usr/bin/dpkg retornou um código de erro (1)

Ao atualizar o Kernel apresentava erro ***Erro rrosub-process /usr/bin/dpkg retornou um código de erro (1)***
Ao ver a matéria do Ricardo Lobo o mesmo menciona que tem que desinstalar firmware de placa de vídeo proprietária, eu não possuo mas tenho de Wi-Fi USB
Verificando ao atualizar apareceu falha na pasta **/var/lib/dkms/8811AU** 
Para corrigir realizei os seguintes procedimentos:
 1. Remoção de  Firmware
Fiz a remoção do diretório com o comando: 
`rm -r /var/lib/dkms/8811AU`
 2. Correção do APT e DPKG
Corrigindo com os comandos: 
    `sudo apt --fix-broken install`
    `sudo dpkg --configure -a`
 3. Limpeza do cache do APT
`sudo apt clean`
 4. Atualizando o Repositório
    `sudo apt update && sudo apt upgrade`
    
 5. Instalando o Kernel
 5.1. Verificando Kernels Disponíveis 
 `sudo apt search linux-image`
 Vai aparecer uma lista semelhante a essa:
> fernando@debian:~$ apt search linux-image
> linux-headers-6.10.9-amd64/testing,now 6.10.9-1 amd64 [installed]  
> Header files for Linux 6.10.9-amd64
> 
> linux-headers-6.10.9-cloud-amd64/testing 6.10.9-1 amd64   Header files
> for Linux 6.10.9-cloud-amd64

No meu caso escolhi:
linux-image-6.10.9-amd64 linux-headers-6.10.9-amd64

 5.2 Atualizar o Kernel
 `sudo apt install linux-image-6.10.9-amd64 linux-headers-6.10.9-amd64`
Reinicia o sistema operacional com o comando `sudo reboot`
Para atualizar o kernel eu segui essa matéria: 
https://linuxdicasesuporte.blogspot.com/2017/07/atualizar-o-kernel-linux-do-debian.html
  



