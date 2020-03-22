# Como instalar ambientes virtuais para o nodejs
**ja deve ter o virtualenv e virtualenvwrapper instalados**

## comandos
  1.1 - cria um ambiente virtual
  - `mkvirtualenv env-node13`
  
  1.2 - Ou entra em um ja criado
  - `workon env-node13`
  
  2 - instala o nodeenv
  - `pip install nodeenv`
  
  3 - verifica a lista de verses de nodes disponiveis
  - `nodeenv --list`
  
  3 - atribui o nodeenv ao ambiente virtual setando a versao do node
  - `nodeenv --node=12.16.1 --python-virtualenv`
  
  4 - saia do ambente virtual
  - `deactivate`
  
  5 - entre novamente no ambiente virtual
  - `workon env-node13`
