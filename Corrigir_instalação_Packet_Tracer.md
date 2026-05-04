# Packet Tracer Corrigindo Biblioteca Libfuse2 Debian Testing

Verificar Debian Tracker https://tracker.debian.org/ https://tracker.debian.org/

O insight para a resolução foi usar o cotexto do vídeo https://www.youtube.com/watch?v=x2JQaXfI-pI ele usou a ferramenta **gdb**  mas no meu caso não precisei pois na mensagem de erro foi bem explicito.

Digita o nome da biblioteca para verificar no caso a fuse2 ela foi removida por estar instavel e tem  uma versão superior mas o Packet Tracer não usa então vamos seguir com a Solução de Contorno.

## Solução de Contorno

### Instalar a versão anterior Dowgrade usado no Debian Stable

### 1- Alterar o repositório Sourcelist do Debian

 Acessar o Sourcelist seu_editor_de_preferencia  ***/etc/apt/sourcelist***

1- Acrescenta  uma linha copia e altera para a versão abaixo conforme o exemplo abaixo.


    deb http://deb.debian.org/debian testing main contrib non-free
    deb http://deb.debian.org/debian bookworm main contrib non-free
    Sair do editor de texto

2- Atualizar o repositório

sudo apt update

3- Verificar a versões disponíveis  nos repositórios pois temos a versão estável e a Teste

    sudo apt policy libfuse2
    #No meu caso não apareceu pois o mesmo foi removido do repositório do Debian conforme verificado no Debian Tracker nesse momento eu ainda não alterei o source list
    
    root@debian:/home/fernando# apt policy libfuse
    Nota: Não é possível encontrar o pacote libfuse
    root@debian:/home/fernando# apt policy libfuse2
    libfuse2:
      Instalado: (nenhum)
      Candidato: (nenhum)
      Tabela de versão:
Feito no meu computador

    fernando@debian:~$ sudo apt policy libfuse2
    libfuse2:
      Instalado: (nenhum)
      Candidato: 2.9.9-6+b1
      Tabela de versão:
         2.9.9-6+b1 500
            500 http://deb.debian.org/debian bookworm/main amd64 Packages


4- Instalar a biblioteca Libfuse2 da versão estável Dowgrade

    #Baixando Atualização do Repositório
    sudo apt update
    #Colocar a Barra para indicar para instalar do repositório da versão anterior
    sudo apt install libfuse2/bookworm 


5- Prevenir Atualizar a biblioteca sem a correção

    # apt-mark marca um aplicativo ou biblioteca hold seguinifica seguro
    sudo apt-mark hold libfuse2


6- Depois que a biblioteca ou programa foi corrigido

    # apt-mark marca um aplicativo ou biblioteca unhold seguinifica libera para atualizar
    sudo apt-mark unhold libfuse2


7- Depois que ficar sabendo que foi resolvido pode remover a linha do repositório no sourcelist para mante-lo limpo e organizado


    deb http://deb.debian.org/debian testing main contrib non-free
    #deb http://deb.debian.org/debian bookworm main contrib non-free
    Sair do editor de texto
    #Atualizar o repositório 
    sudo apt update
