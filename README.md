# Git - Guia prático

## Sua identidade

A primeira coisa que você deve fazer quando instalar o Git é definir o seu nome de usuário e endereço de e-mail. Isso é importante porque todos os commits no Git utilizam essas informações, e está imutavelmente anexado nos commits que você realiza:

    git config --global user.name "Seu nome"
    git config --global user.email seu-email@exemplo.com

Relembrando, você só precisará fazer isso uma vez caso passe a opção `--global`, pois o Git sempre usará essa informação para qualquer coisa que você faça nesse sistema.

## Criando um novo repositório

Crie uma nova pasta, abra-a e execute o comando

    git init

para criar um novo repositório.

## Clonando um repositório

Crie uma cópia de trabalho em um repositório local executando o comando

    git clone /caminho/para/o/repositório

Quando estiver usando um servidor remoto, seu comando será

    git clone usuário@servidor:/caminho/para/o/repositório

## Adicionar & Confirmar (add & commit)

Você pode propor mudanças (adicioná-las ao `**Index**` ) usando

    git add <arquivo>

para um arquivo em específico, ou

    git add * or git add .

para todos os arquivos.

Este é o primeiro passo no fluxo de trabalho básico do git. Para realmente confirmar estas mudanças (isto é, fazer um _commit_), use

    git commit -m "comentário sobre as alterações"

Agora o arquivo foi enviado para o `**HEAD**` , mas ainda não para o repositório remoto.

Para verificar o status dos arquivos, você deve digitar o comandos

    git status

## Enviando as alterações (push)

Antes de realizar o git push, você deve mudar a branch do git para main com o seguinte comando

    git branch -M main

Após ter feito isso, as suas alterações agora estão no `**HEAD**` da sua cópia de trabalho local. Para enviar estas alterações ao seu repositório remoto, execute

    git push origin main

Você pode alterar o _main_ para qualquer ramificação (_branch_) desejada, enviando suas alterações para ela.

Se você não clonou um repositório existente e quer conectar seu repositório local a um servidor remoto, você deve adicioná-lo com

    git remote add origin <servidor>

Agora você é capaz de enviar suas alterações para o servidor remoto selecionado.

## Atualizar Pull

Para atualizar seu repositório local com a mais nova versão, execute

    git pull

na sua pasta de trabalho. Isso vai atualizar o seu repositório, caso alguém tenha feito alguma alteração.
