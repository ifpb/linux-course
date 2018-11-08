# Usando a Linha de Comandos do Linux

[\# 01 - Apresentação do MiniCurso](#-01---apresentacao-do-minicurso);
[\# 02 - História do Linux](#-02---história-do-linux);
[\# 03 - Distribuições e Interfaces](#-03---distribuições-e-interfaces);
[\# 04 - Comandos Básicos](#-04---comandos-basicos);
[\# 05 - Comandos Intermediários](#-05---comandos-intermediarios);
[\# 06 - Comandos Avançados](#-06---comandos-avancados);
[\# 07 - Instalação](#-07---instalacao);
[\# 08 - Referências](#-08---referencias);

---
## \# 01 - Apresentação do MiniCurso

**Evento**: SECT IFPB 2018
**Data**: 23 e 24 de outubro de 2018
|Ministrante| Elionildo da Silva Menezes
|---|:---|
|Monitor| Edson Luís Vieira de Almeida
|Monitor| Lucas Carvallho
|Monitor| Miguel Rodrigo Belarmino Cabral

O sistema operacional Linux pode ser encontrado em uma variedade de dispositivos, incluindo desktops, notebooks, smartphones e servidores de rede. Ele está disponível para uso tanto por meio de interface gráfica (voltada normalmente para aplicações cotidianas como navegação na Web, envio de mensagens de correio eletrônico etc.) como em um ambiente de linha de comandos para permitir a administração de serviços nele configurados (servidores Web, servidores de banco de dados etc.) e disponibilizados para usuários de uma rede. Mesmo nos dias atuais, esse ambiente de linha de comandos é útil, pois permite a instalação e execução do sistema operacional com menos recursos de hardware (processador, memória RAM e armazenamento) quando comparados aos requisitos para execução de interface gráfica.

Adicionalmente, é possível automatizar a execução de tarefas repetitivas como, por exemplo, a criação de centenas de contas de usuários utilizando um pequeno script. Nesse contexto, a proposta deste minicurso é apresentar o sistema operacional Linux, mostrando a sua instalação e alguns comandos básicos para atividades como administração de diretórios, arquivos, usuários e rede. A abordagem do minicurso contemplará exposições teóricas acompanhadas de atividades práticas realizadas na distribuição Debian.


---

## \# 02 - História do Linux
#### O que é um Sistema Operacional?

Segundo Silberschatz, A. 2008, um sistema operacional:
- Fornece o ambiente dentro do qual os programas são executados
- Atua como um intermediário entre usuário e o hardware do computador
- É o software que controla o hardware do computador

#### Origem do Linux
- Surgiu em 1991
- Criado por Linus Torvalds
- Baseado no sistema operacional UNIX


#### Sobre o Linux
- É um kernel e não um sistema operacional completo
- É um software de código aberto e gratuito
- Possui versões para arquitetura de hardware de 32 e 64 bits
- Executa em desktops, servidores, tablets/smartphones, arduino...

---

## \# 03 - Distribuições e Interfaces
#### Distribuições Linux

Uma distribuição Linux é formada pelo kernel e um conjunto de programas.

- Distribuições comerciais
    - [Red Hat](https://www.redhat.com/en)

- Distribuições comunitárias
    - [Debian](https://www.debian.org/)
    - [Ubuntu](https://www.ubuntu.com/)
    - [Linux Mint](https://www.linuxmint.com/)
    - [Fedora](https://getfedora.org/pt_BR/)
    - [CentOS](https://www.centos.org/)

#### Distribuição Debian
- É uma distribuição comunitária, com o desenvolvimento garantido independentemente de qualquer restrição comercial; seus objetivos são, portanto, essencialmente de natureza técnica, o que parece favorecer a qualidade geral do produto
- De todas distribuições comunitárias, é muito significativa sob muitos aspectos: números de colaboradores, número de pacotes de programas disponíveis, e anos de existência contínua
- Estatisticamente, novas versões são lançadas a cada 18 a 24 meses, um planejamento que é agradável aos administradores
- Está disponível para diversas arquiteturas
- Atualmente, está na versão 9, denominada stretch

##### Versões do Debian
- Estável    
    - Corresponde à versão oficial mais recente do sistema operacional
    - É a versão de produção do Debian, sendo, portanto, seu uso fortemente recomendado em relação às outras versões

- Testing
    - Contém pacotes que ainda não foram aceitos na versão "estável (stable)", mas estão na fila para tanto
    - A sua principal vantagem é possuir versões mais recentes de software

- Instável
    - É nesta versão que o desenvolvimento ativo do Debian ocorre
    - Geralmente é utilizada por desenvolvedores e por aqueles que podem aceitar os riscos de falhas e incertezas quanto ao funcionamento normal do sistema

#### Interfaces Gráficas
- KDE
- GNOME
- Xfce
- LXDE
- MATE
- Cinnamon

#### Interface (Terminal) Linha de Comandos
- Interface de comandos consomem menos recursos do sistema (CPU, RAM, disco) do que as interfaces gráficas
- De acordo com o [Guia Foca Linux](http://www.guiafoca.org/): “Comandos são ordens que passamos ao sistema operacional para executar uma determinada tarefa”
- Comandos são mais customizáveis por causa da diversidade de opções
- Possibilidadede criação de script para automatizar tarefas

##### Comandos

- Os comandos são case sensistive, ou seja, há distinção entre maiúsculas e minúsculas

- Comandos internos
    - Estão dentro de um shell (interpretador de comandos)
    - Para executar, não precisam ser procurados no disco
    - Não criam processos
    - Exemplos incluem `cd`, `alias`, `bg`, `fg`, `kill`, `help`, `exit` e `logout`

- Comandos externos
    - Estão dentro de diretórios no disco, como `/bin` e `/sbin`
    -O sistema precisa acessar o disco quando esses comandos são executados
    - Correspondem à maioria dos comandos do Linux
    - Exemplos incluem `ls`, `cp`, `rm`, `mv`, `mkdir` e `rmdir`

- Sintaxe básica

```bash
comando  [opções]  [parâmetros]
```

- As opções são usadas para controlar como o comando será executado
    - Podem ser passadas ao comando utilizando um hífen (`-`) ou dois hifens (`--`) seguidos e sem espaços
    - O hífen deve ser seguido por uma ou mais letras
    - Os dois hifens são seguidos por uma palavra
    - Há casos em que o uso de “`-`” ou “`--`“   produzem o mesmo resultado e há caso que os resultados são diferentes

- Os parâmetros são usados para identificar o caminho, origem, destino, entrada padrão ou saída padrão que será passada ao comando

> - No Shell BASH existe um recurso que permite autocompletar um comando ou parâmetro, bastando que o usuário digite apenas parte do comando/parâmetro e pressione a tecla TAB.
> - Por exemplo, para digitar o comando clear, o usuário pode digitar cl e pressionar a tecla TAB

---

## \# 04 - Comandos Básicos
O prompt para a conta do usuário root, isto é, o administrador do sistema, termina com o caractere #:
```bash
root@pcdebian:~# _
```
O prompt para a conta do usuário comum, isto é, sem poderes administrativos, termina com o caractere $:
```bash
usuario@pcdebian:~$ _
```
Para obter uma descrição sobre cada comando no Linux:
```bash
usuario@pcdebian:~$ man nome-do-coamndo
```
- Para sair, pressione `q`.

- Para buscar algum termo, digite: `/termo-a-ser-buscado`

---

- `pwd`: Retorna o diretório atual

---

- O diretório `/` é conhecido como o diretório raiz do sistema;
- O diretório de trabalho (home) do usuário root é `/root`;
- O diretório de  trabalho do usuário comum, normalmente, é `/home/conta-do-usuário`

---

- `touch`: Pode ser usado para criar arquivos
```bash
usuario@pcdebian:~$ touch arq1 arq2 arq3
```
Cria os arquivos arq1, arq2 e arq3, caso não existam.

---

- `ls`: Lista o conteúdo do diretório atual. Algumas opções bastante utilizadas são: `-a`, `-l`, `-R`.
- `dir`: Faz o mesmo que o comando `ls`
- `date`: Verifica a data e hora atual do sistema
- `clear`: Limpa a tela do terminal. `Crtl + L` tem o mesmo efeito
- `cat`: Visualiza o conteúdo de um arquivo
- `more`: Visualiza o conteúdo de um arquivo. Caso o arquivo tenha mais linhas que a quantidade suportada pelo vídeo do computador, ele será mostrado de forma pausada.

```bash
usuario@pcdebian:~$ cat /etc/passwd
```

```bash
usuario@pcdebian:~$ more /etc/passwd
```

Cat pode ser usado para criar arquivos, bastando combiná-lo com o redirecionador `>`. Para encerrar, basta pressionar `Ctrl + D`, que é um sinal fim de arquivo (EOF).

```bash
usuario@pcdebian:~$ cat > nome-do-arquivo.txt
meu primeiro texto no Linux
Ctrl+D
```

Se o arquivo já existir, ele será sobrescrito, ou seja, apagará o que existe nele e colocará o novo texto.
Para isso não ocorrer, pode-se usar o redirecionador `>>`, assim, o texto será adicionado ao final do arquivo.

```bash
usuario@pcdebian:~$ cat >> nome-do-arquivo.txt
mais uma linha no meu primeiro texto no Linux
Ctrl+D
```

Cat é usado para concatenar (unir) conteúdos de arquivos.

```bash
usuario@pcdebian:~$ cat arq1 arq2 arqN > arquivo-com-tudo.txt
usuario@pcdebian:~$ cat arq3 arq4 arqN >> arquivo-com-tudo.txt
```

Uso de caracteres curingas para manipulação de arquivos/diretórios:

- `*`: Significa qualquer caracter e qualquer quantidade
- `?`: Significa qualquer caracter, mas apenas UM

```bash
# Listar arquivos com extensão txt
usuario@pcdebian:~$ ls *.txt

# Listar arquivos que começam com a letra a
usuario@pcdebian:~$ ls a*

# Listar arquivos que tenha apenas um caracter, com qualquer extensão
usuario@pcdebian:~$ ls ?.*
```

- `cd`: Muda de diretório
```bash
# Mover-se para o diretório home do usuário
usuario@pcdebian:~$ cd ~

# Mover-se para o diretório anterior
usuario@pcdebian:~$ cd -

# Mover-se para o diretório 'documentos' que está no diretório atual
usuario@pcdebian:~$ cd documentos

# Mover-se para o diretório 'init.d' usando o caminho completo
usuario@pcdebian:~$ cd /etc/init.d

# Mover-se para o diretório 'init.d' usando o caminho relativo
usuario@pcdebian:~$ cd ../../etc/init.d
```
- `..`: Diretório que está um nível acima, vulgo diretório pai
- `.`: Diretório atual

---

- `mkdir`: Cria um diretório

```bash
usuario@pcdebian:~$ mkdir minicurso
```

---

- `cp`: Copiar arquivos

```bash
# Copiar arquivo src para dst
usuario@pcdebian:~$ cp src dst

# Copiar arquivos arq1, arq2 e arq3 para o diretório dst_d
usuario@pcdebian:~$ cp arq1 arq2 arq3 dst_d
```

- `tree`: Constroe um diagrama da árvore dos diretórios

```bash
root@pcdebian:~# apt install tree
usuario@pcdebian:~$ tree
```

- `mv`: Mover ou renomear arquivos/diretórios

```bash
# Mover um arquivo
usuario@pcdebian:~$ mv dir1/arq dir2/

# Renomear um arquivo
usuario@pcdebian:~$ mv arq arquivo

# Mover vários arquivos para um diretório
usuario@pcdebian:~$ mv arq1 arq2 arq3 diretorio/
```

- `rm`: Remover arquivos ou diretórios

```bash
usuario@pcdebian:~$ rm arquivo
usuario@pcdebian:~$ rm -r diretorio

# Remover sem perguntar/confirmar
usuario@pcdebian:~$ rm -rf diretorio
```

- `rmdir`: Remove diretórios vazios

```bash
usuario@pcdebian:~$ rmdir diretorio-vazio
```

- `poweroff`: Desliga o sistema.
- `shutdown now`: O mesmo que poweroff.
- `reboot`: Reinicia o sistema.
- `shutdown -r now`: O mesmo que reboot.

```bash
root@pcdebian:~# poweroff
root@pcdebian:~# shutdown now
root@pcdebian:~# reboot
root@pcdebian:~# shutdown -r now
```

---

## \# 05 - Comandos Intermediários
### Permissões básicas no Linux
- As permissões de acesso protegem o sistema de arquivos Linux do acesso indevido de pessoas ou programas não autorizados
- As permissões são definidas para os arquivos e diretórios existentes no sistema, inclusive aqueles criados pelos seus usuários
- A ideia básica da segurança no sistema GNU/Linux é definir o acesso aos arquivos por **dono** (_user_), **grupo** (_group_) e **outros usuários** (_others_)
- Dono:
    - É a pessoa que criou o arquivo ou o diretório.
    - Por padrão, o nome do dono do arquivo/diretório é o mesmo do usuário usado para acessar o sistema.
    - Somente o dono (ou o root) pode modificar as permissões de acesso do arquivo
- Grupo:
    - Permite que vários usuários diferentes tenham acesso a um mesmo arquivo (já que, em princípio, somente o dono poderia ter acesso ao arquivo)
    - Cada usuário pode fazer parte de um ou mais grupos e então acessar arquivos que pertençam ao mesmo grupo que o seu (mesmo que estes arquivos tenham outro dono)
- Outros:
    - É a categoria de usuários que não são donos ou não pertencem ao grupo do arquivo

#### Tipos de permissões
- **r**: Permissão de leitura para arquivos. Caso for um diretório, permite listar seu conteúdo (através do comando ls, por exemplo) 
- **w**: Permissão de gravação para arquivos. Caso for um diretório, permite a gravação de arquivos ou outros diretórios dentro dele. Para que um arquivo/diretório possa ser apagado, é necessário o acesso a gravação
- **x**: Permite executar um arquivo (caso seja um programa executável). Caso seja um diretório, permite que seja acessado através do comando cd 

#### Exemplo de permissões

```bash
-rwxr-xr-- 1 usuario users    0 out  6 22:40 arquivo_teste
drwxr-xr-x 2 usuario users 4096 out  6 22:40 diretorio_teste
```

- A primeira letra diz qual é o tipo do arquivo. Caso tiver um "d" é um diretório, um "l" um link a um arquivo no sistema , um "-" quer dizer que é um arquivo comum
- Da segunda a quarta letra (**rwx**) dizem qual é a permissão de acesso ao dono do arquivo. Neste caso usuario ele tem a permissão de ler (**r** - read), gravar (**w** - write) e executar (**x** - execute) o arquivo_teste
- Da quinta a sétima letra (**r-x**) diz qual é a permissão de acesso ao grupo do arquivo. Neste caso todos os usuários que pertencem ao grupo users têm a permissão de ler (**r**), e também executar (**x**) o arquivo_teste 
- Da oitava a décima letra (**r--**) diz qual é a permissão de acesso para os outros usuários. Neste caso todos os usuários que não são donos do arquivo teste têm a permissão somente para ler o conteúdo do arquivo 

#### Gerenciando permissões básicas

```bash
chmod [opções] [permissões] [diretório/arquivo]
```

- Muda a permissão de acesso a um arquivo ou diretório
- Não muda permissões de links simbólicos, as permissões devem ser mudadas no arquivo alvo do link
- Admite os modos simbólico ou absoluto/octal para o parâmetro [permissões]
- Permissões
    - `ugoa`: Controla que nível de acesso será mudado. Especificam, em ordem, usuário (`u`), grupo (`g`), outros (`o`), todos (`a`)
    - `+ - = `: `+` acrescenta a permissão, `-` retira a permissão do arquivo e `=` define a permissão exatamente como especificado
    - `rwx `: `r` permissão de leitura do arquivo. `w` permissão de gravação. `x` permissão de execução (ou acesso a diretórios)
- Permissões em modo absoluto ou octal

r|w|x
-|-|-
4|2|1

Condições de permissão:
0: sem permissão de leitura, escrita e execução
1: permissão apenas de execução
2: permissão apenas de escrita
3: permissão de execução e escrita (2+1)
4: permissão apenas de leitura
5: permissão de leitura e execução (4+1)
6: permissão de leitura e escrita (4+2)
7: permissão de leitura, escrita e execução (4+2+1)
Exemplos:
```bash
usuario@pcdebian:~$ chmod 764 arquivo_teste
-rwxrw-r-- 1 usuario users 1024 out  6 22:40 arquivo_teste # resultado

usuario@pcdebian:~$ chmod 40 arquivo_teste
----r----- 1 usuario users 1024 out  6 22:40 arquivo_teste # resultado

usuario@pcdebian:~$ chmod 751 arquivo_teste
-rwxr-x--x 1 usuario users 1024 out  6 22:40 arquivo_teste # resultado
```

---

#### Alguns comandos intermediários

- `chown [opções] dono[:grupo] arquivo`: Mudar dono e/ou grupo do arquivo
- `chgrp [opções] grupo arquivo`: Mudar grupo do arquivo
- `find`: Localizar arquivos / diretórios
- `echo`: Usado para exibir uma mensagem, conteúdo de uma variável ou mesmo o resultado da execução de um comando
- `sort`: Usado para ordenar linhas de arquivos de texto
- `grep`: Usado para buscar algum padrão em arquivos
- `wc`: Usado para contar linhas, palavras e caracteres em um arquivo

---

## \# 06 - Comandos Avançados

- `adduser user`: cria usuário com login user
- `passwd user`: muda a senha do usuário user
- `uname -a`: a versão do Kernel do sistema
- `lsb_release -a`: ver qual a distribuição Linux instalada e sua versão
- `ip addr show`: Mostra as configurações da(s) interface(s) de rede
- `ip addr show dev enp0s3`: Mostra as configurações da interface de rede enp0s3
- `ip addr flush dev enp0s3`: Apaga as configurações da interface de rede enp0s3
- `ip addr add 192.168.0.1/24 dev enp0s3`: Adiciona o IP/Máscara às configurações da interface de rede enp0s3

Para definir configurações de rede estáticas em uma interface de rede mesmo após reiniciar o sistema, edite o arquivo `/etc/network/interfaces`

```bash
auto lo
iface lo inet loopback

auto enp0s3
iface enp0s3 inet static
    address 192.168.0.1/24
    gateway 192.168.0.254
    dns-nameservers 8.8.8.8 8.8.4.4
```

Para ativar as configurações é necessário reiniciar o serviço de rede:

```bash
root@pcdebian:~# systemctl restart networking
```

Os softwares são encontrados na forma de pacotes, no debian. Esses pacotes são arquivos com a extensão `.deb`. Eles podem ser “baixados” de servidores que atuam como repositórios de pacotes. No debian, é possível verificar/configurar uma lista de repositórios editando o arquivo /etc/apt/sources.list. Um exemplo de repositório configurado nesse arquivo é mostrado na linha seguinte:
`deb http://ftp.br.debian.org/debian stretch main`

- `apt update`: atualizar lista de pacotes usando o repositório do sources.list
- `apt upgrade`: atualiza todos os pacotes instalados no sistema
- `apt install gcc`: instala o pacote gcc e suas dependências
- `gcc meu_programa.c –o meu_programa`: compilar arquivo em C, onde meu_programa.c é o arquivo e meu_programa o executável

Para executar o programa compilado:

```bash
usuario@pcdebian:~$ ./meu_programa
```

---

## \# 07 - Instalação

Demonstração de instalação básica da distribuição Debian versão 9.5 64 bits.

1 - Baixe a distro básica:
[debian-9.5.0-amd64-netinst.iso](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-9.5.0-amd64-netinst.iso)

---
2- Crie uma máquina virtual no [VirtualBox](https://www.virtualbox.org/):
- Clique em Novo
- Nome: pc01
- Tipo: Linux
- Versão: Debian (64-bit)
- Próximo
- 1024 MB de RAM
- Próximo
- Criar um novo disco rígido virtual agora
- Criar
- VDI (VirtualBox Disk Image)
- Dinamicamente alocado
- 20,00 GB
- Criar

---
3 - Insira a imagem ISO de instalação do sistema Linux
- Com pc01 selecionado, clique em Configurações
- Selecione Armazenamento, drive óptico
- Selecionar arquivo de disco optico virtual
- Selecione a .iso que baixou
- Clique em Ok

---
4 - Instale
- Clique em Iniciar
- Install
- Selecionar um idioma: Português do Brasil
- Selecionar sua localidade: Brasil
- Configure o teclado: Português Brasileiro
- Nome de Máquina: pcdebian
- Nome de domínio:
- Senha do root: root
- Informe novamente a senha para verificação: root
- Nome completo para o novo usuário: usuario
- Nome de usuário para sua conta: usuario
- Escolha uma senha para o novo usuário: usuario
- Informe novamente a senha para verificação: usuario
- Configurar relógio: Paraíba
- Particionar discos: Assistido - usar disco inteiro
- Selecione o disco para ser particionado: SCSI1 (0,0,0) (sda) - 21.5 GB ATA VBOX HARDDISK
- Esquema de particionamento: Todos os arquivos em uma partição (para iniciantes)
- Finalizar o particionamento e escrever as mudanças no disco
- Escrever mudanças nos discos? Sim
- Ler outro CD ou DVD? Não
- País do espelho do repositório Debian: Brasil
- Espelho do repositório Debian: ftp.br.debian.org
- Informação sobre proxy HTTP: 
- Participar do concurso de utilização de pacotes? Não
- Desmarque as opções
  - ambiente de área de trabalho no Debian
  - Servidor de impressão
  - utilitários de sistema padrão
- Instalar o carregador de inicialização GRUB no registro mestrede inicialização? Sim
- Dispositivo no qual instalar o carregador de inicialização: /dev/sda
- Instalação completada: Continuar

## \# 08 - Referências
* SILBERSCHATZ, A. Sistemas Operacionais com Java. 7ª. Edição, 2008. Elsevier.
* https://debian-handbook.info/browse/pt-BR/stable/sect.why-debian-stable.html
* https://www.debian.org/releases/index.pt.html

* http://www.guiafoca.org/cgs/guia/inic_interm