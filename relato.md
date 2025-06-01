# Atividade 02 - Introdução a linux usando docker no windows

#### Aluno: Pedro Lucas Xavier da Fonseca

#### Data 09/05/2025

## Introdução

A atividade teve como objetivo realizar uma introdução a comandos básicos do Linux, como comandos de navegação, manipulação de arquivos, gerenciamento de pacotes, permissões e processos, a partir de um container Docker do Fedora, simulando uma máquina virtual Linux no Windows.

## Relato

### 1. Iniciar um contêiner Fedora

Primeiramente, com o Docker já instalado, executei o comando para iniciar um conteiner a partir de uma imagem do Fedora. Como a imagem não existia na minha máquina foi necessário baixa-la.

![Criando conteiner Fedora](imagens/Captura%20de%20tela%20de%202025-05-24%2011-45-43.png)

### 2. Navegação básica

Com o container inicializado passei a testar comando básicos de navegação como `pwd` que retorna o caminho até o diretório em que estou no momento, `cd [nome do diretório]` para navegar entre diretórios. Usamos `cd ~` para navegar até o diretório home e `cd ..` para voltar para o diretório logo acima. Também usei o comando `ls` para listar subdiretórios e/ou arquivos do diretório atual e `mkdir` para criar um novo diretório.

![Navegando entre diretórios](imagens/Captura%20de%20tela%20de%202025-05-24%2011-49-19.png)

### 3. Manipulação de arquivos

A seguir continuei utilizando comandos de navegação e criei um novo arquivo, utilizando o comando `touch`, no diretório home, chamado `arquivo1.txt`. Manipulei esse arquivo, primeiro, renomeando-o para `documento.txt` com o comando `mv [nome atual][novo nome]`, depois naveguei para o diretório `atividades` e criei um diretório chamado `backup`. Nesse diretório executei o comando `cp ~/documento.txt backup/` que copiou o arquivo anterior para o diretório recém criado `backup`. Para finalizar, retornei ao diretório `home` e utilizando o comando `rm [nome do arquivo]` solicitei a exlusão do arquivo original. Confirmei e o arquivo foi excluido.

![Manipulando arquivos](imagens/Captura%20de%20tela%20de%202025-05-24%2011-55-43.png)

### 4. Gerenciamento de pacotes

Nessa etapa utilizei o comando `dnf` para gerenciar pacotes. Primeiramente atualizei a lista de pacotes.

![Atualizando lista de pacotes](imagens/Captura%20de%20tela%20de%202025-05-24%2011-58-24.png)

Em seguida, testei outros comandos de gerenciamento para **instalar** e **desinstalar** pacotes. No exemplo, primeiro instalei o editor de texto `nano`, verifiquei se a instalação havia sido feita corretamente e por fim, desinstalei o pacote.

![Instalando e desinstalando nano](imagens/Captura%20de%20tela%20de%202025-05-24%2012-02-05.png)

### 5. Permissões de arquivos

Nessa etapa do exercício criei um arquivo `script.sh` com a finalidade de testar o comando `chmod` que permite modificar as permissões de **leitura**, **escrita** e/ou **execução** de arquivos. Após a criação do arquivo executei o comando `chmod u+x script.sh` que concede ao usuário proprietário (u) permissão para executar o arquivo (x). Após modificar a permissão verifiquei a alteração com o comando `ls -l script.sh`.

![Criando arquivo script.sh](imagens/Captura%20de%20tela%20de%202025-05-24%2012-04-47.png)

### 6. Processos em execução

Seguindo, precisei instalar o comando `ps` para poder monitorar os processos em execução. Utilizei o já conhecido comando `dnf install` para instalar o pacote referente ao comando `ps`. Após a instalação listei os processos em execução com o comando `ps aux` e obtive como retorno o próprio processo `ps aux` bem como o processo de execução do terminal `/bin/bash`. Executei um processo em segundo plano com o comando `sleep 60 &` e busquei o PID desse processo com o comando `ps aux | grep sleep`. Com a informação do PID executei o comando `kill [PID]` para encerrar o processo e verifiquei novamente com `ps aux`.

![Verificando e matando processos](imagens/Captura%20de%20tela%20de%202025-05-23%2015-05-45.png)

### 7. Encerrando o contêiner

Por fim, com o comando `exit` sai do container, e executei `docker rm [nome da imagem]` para remover o container.

![Verificando e matando processos](imagens/Captura%20de%20tela%20de%202025-05-24%2012-13-54.png)

## Conclusão

Apesar de já ter certa familiaridade com o terminal do Linux, inclusive com alguns dos comandos utilizados durante o exercício, eu sempre utilizei distribuições baseadas no Debian, como Ubuntu, Mint e Pop OS. Dessa forma, pude traçar alguns paralelos entre esses sistemas, como por exemplo, o uso do comando `dnf` para gerenciamento de pacotes, enquanto nas distros baseadas no Debian é mais comum o uso do comando `sudo`. Outra diferença que notei é o fato de alguns pacotes de comandos, como o `clear` e o `ps` necessitarem de instalação.