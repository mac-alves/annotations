# correção do bug de audio presente no linux mint 19.3
As vezes com a instalação do novo kernel pode ocorrer de o linux mint não reconhecer a placa de áudio do computador ou atribui uma placa fictícia que não funciona. Para resolver isso executar os seguintes comandos:

## 1ª alternativa

**Executar os comando apenas uma vez cada**

```
  echo "options snd-hda-intel dmic_detect=0" | sudo tee -a /etc/modprobe.d/alsa-base.conf
  echo "blacklist snd_soc_skl" | sudo tee -a /etc/modprobe.d/blacklist.conf  
```

## 2ª alternativa
  - abrir o arquivo ``` /etc/modprobe.d/alsa-base.conf ``` como adminstrador, ou atravez do comando: 
```
  sudo nano /etc/modprobe.d/alsa-base.conf
```
  - Adcionar o seguinte comando no final do arquivo. ***(faça somente isso para não ocasionar erros)***
```
  options snd-hda-intel dmic_detect=0
```

  - abrir o arquivo ``` /etc/modprobe.d/blacklist.conf ``` como adminstrador, ou atravez do comando: 
```
  sudo nano /etc/modprobe.d/blacklist.conf
```
  - Adcionar o seguinte comando no final do arquivo. ***(faça somente isso para não ocasionar erros)***
```
  blacklist snd_soc_skl
```


### OBS
  - Caso o procedimento não der certo basta reverter os arquivos para o estado anterior removendo as linhas adicionadas
