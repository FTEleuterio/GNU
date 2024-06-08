$ sudo virsh net-list --all Se aparecer inative

Solução $ sudo virsh net-start default

fonte: https://www-xmodulo-com.translate.goog/network-default-is-not-active.html?_x_tr_sl=auto&_x_tr_tl=pt&_x_tr_hl=pt-BR


Corrigir Problema de Rede NAT no Gerenciador de Máquinas Virtuais

fernando@debian:~$ nano /etc/libvirt/qemu
fernando@debian:~$ sudo nano /etc/libvirt/qemu
fernando@debian:~$ sudo virsh net-list --all
 Name      State      Autostart   Persistent
----------------------------------------------
 default   inactive   no          yes

fernando@debian:~$ sudo virsh net-autostart default
Network default marked as autostarted

fernando@debian:~$ sudo virsh net-start default
Network default started

fernando@debian:~$ sudo virsh net-list --all
[sudo] senha para fernando: 
 Name      State    Autostart   Persistent
--------------------------------------------
 default   active   yes         yes

fernando@debian:~$ 

Fonte: 
Sombex
https://www.youtube.com/watch?v=nzRY8suaPX8