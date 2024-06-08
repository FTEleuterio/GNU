######Resolver problema na Instalação do Virtualizador Virt-Manager######

## Dica para ver se o Proessador é compatível com Virtualização 

Alguns processadores não suportam virtualização aí tem que ser por VBox e creio que 6.0 se 6.1 já vai dar conflitos  ... e tem mais relacionado com libvpx5 que em Debian Testing já não existe (passou a libvpx6).

para saber se o processador suporta virtualização por vitmanager:

egrep '(vmx|svm)' --color=always /proc/cpuinfo

se nada retornar é indicação que o processador não suporta virt.

### Instalação
##para ver se falta alguma dependência
apt install -f

## Para corrigir o meu problema precisei seguir o procedimento baixo:
Depois apt purge lvm2
apt autoremove
apt install virt-manager

#Para ver se está pronto
dpkg -l |grep libvirt

#Pra ver se já está rodando rode:
service libvirtd status

#Colocar meu usuário no grupo do virt
É interessante colocar seu usuário no grupo libvirt rodando:
adduser <nome-do-seu-usuario> libvirt

### Virtual Box não pode ser instalado em Debian 'testing'.  VB depende de libvpx5 mas libvpx6 está instalado.####

Quando estiver instalado o Virt muda a opção LXC para QEMU/KVM para instalar o Sistema Operacional com o arquivo .iso

Para tirar oouse do pc virtualizo Ctrl + Alt