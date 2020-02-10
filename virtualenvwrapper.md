# Como instalar o virtualenvwrapper no linux
*ambientes virtuais em python com o Virtualenv e gerenciador de ambientes virtuais python com virtualenvwrapper*

## instalação
**digitar em um termninal**
```   
sudo pip install virtualenv virtualenvwrapper 
sudo rm -rf ~/.cache/pip
```

**pacotes instalados.. adcionar o seguinte codigo no fim do arquivo ~/.profile**
```
# virtualenv and virtualenvwrapper
export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
source /usr/local/bin/virtualenvwrapper.sh
```

*voltar para o termianl e digitar*
```
source ~/.profile
```

## Comandos uteis
**criar um ambiente vitrual**<br />
*com python 3*
```
mkvirtualenv nome-do-ambente -p python3
```

*com python 2*
```
mkvirtualenv nome-do-ambente -p python2
```

**entrando em um ambiente**
```
workon nome-do-ambiente
```

**saindo de um ambiente**
```
deactivate
```

**remover um ambiente**
```
rmvirtualenv nome-do-ambiente
```

**gerar arquivo de instalaçõa com pip**
```
pip freeze > requirements.txt
```