O comando abaixo resolve esse problema de configuração de teclado, onde a tecla ponto (.) do teclado numérico expressa vírgula (,) em vez de ponto. 

Essa é uma dica valiosa pra quem utiliza muito o teclado numérico ou para quem quer, simplesmente, corrigir esse problema. 

1. Abra o terminal 

2. Digite o comando: 

> $ xmodmap -e 'keycode 129 = period' 

Agora a tecla de ponto (.) irá expressar o ponto normalmente nos programas.
