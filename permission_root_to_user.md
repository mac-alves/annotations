# Instrução para recuperar os privilégios de root de um usuário (Linux mint)

- Caso, por algum motivo, acabe deletando as permissões de root do usuário e não
consiga mais rodar comandos que precisam de privilégios seguir esses passos.

## (1 - Etapa) Senha do root

- Caso não possua a senha do usuário root seguir esses passos, caso ja possua
seguir para a etapa 2.

    - reiniciar o computador, entrar na tela de grup clicar a tecla e
    - ira aparecer uma tela com um mont de textos. Verificar a linha: 
        (<$$> -> indica que tem mais textos, ou não, mas que varia de maquina pra maquina)

        `linux          /boot/vmlinuz-4<$$> ro quiet splash <$$>`

    - editar somente esta linha para que fique assim: 
        `linux          /boot/vmlinuz-4<$$> rw quiet init=bin/bash`

    - em outras palavras, trocar: `ro quiet splash <$$>` por `rw quiet init=bin/bash` para que o sistema inicialize diretamente no terminal root do sistema
    - para alterar a senha do root digite o comando: `passwd root`
    - apos informar a nova senha e confirmar a nova senha deve-se reiniciar o sistema com o comando: `exec /sbin/init 6`

## (2 - Etapa) Setar permissões ao usuario

- Ja logado com o usuario que deseja setar as permissões ou mesmo logado com o usuario root seguir os passos a seguir.
    - logar como root no terminal (caso não esteja): `sudo su`
    - listar quais grupos o usuário pertence atualmente: `grep mac /etc/group` onde `mac` é o seu nome de usuário
    - para que o usuário tenha as permissões do sistema igual de quando foi instalado ele deve contar em todos os seguintes grupos:
    ```
    root
    adm
    cdrom
    sudo
    dip
    plugdev
    lpadmin
    sambashare
    docker
    ```
    - caso não esteja nesses grupos pode inserir executando o comando: `usermod -aG root mac` onde `root` é o nome do grupo e `mac` o nome do usuário. Ao final a saida do comando `grep mac /etc/group` deve ficar semelhante a isto:
    ```
    root:x:0:mac
    adm:x:4:syslog,mac
    cdrom:x:24:mac
    sudo:x:27:mac
    dip:x:30:mac
    plugdev:x:46:mac
    lpadmin:x:114:mac
    mac:x:1000:
    sambashare:x:134:mac
    docker:x:999:mac
    ```
    - reiniciar o sistema para que possa fazer efeito.