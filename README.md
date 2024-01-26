# Projeto em pausa

# Automações web em segundo plano
Como Rodar automações web em segundo plano
Artigo escrito por [Wesley Pereira](https://github.com/wesleyp846)


>## Introdução

Este artigo ensina como rodar automações web construídas com Selenium em segundo plano.

A ideia é que o navegador abra e execute toda a automação de forma invisível, sem interface gráfica.

Isso permite executar autos de teste, coletas de dados, processamentos em lote, entre outras automações, sem precisar ver o navegador abrindo e fechando a cada execução.

> Inspirado em um video no youtubo da Hashtag Treinamentos
>> [Hashtag Treinamentos](https://www.youtube.com/watch?v=nPNWmB7NVRU&list=WL&index=8)


>## Passo a Passo

Primeiro, deve-se ter um código de automação web já funcionando, como esse exemplo básico em `Selenium` com `Python`:
```
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.chrome.service import Service  
servico = Service(ChromeDriverManager().install())  

navegador = webdriver.Chrome(service=servico)
```

>## Modificando para segundo plano

Importe as opções do webdriver:

```
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
```

## Configure o navegador para abrir em segundo plano:

```
opcoes = Options()
opcoes.add_argument('--headless')
  
servico = Service(ChromeDriverManager().install())
  
navegador = webdriver.Chrome(service=servico, options=opções)
```

O restante do código de automação pode ser mantido.

Ao executar agora, o navegador irá abrir e processar toda a automação sem interface, em background.

>## Vantagens

* Menos recursos consumidos da máquina
* Processamento mais rápido
* Pode rodar em servidores remotos sem interface gráfica
