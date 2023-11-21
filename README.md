# Automacoes_web_segundo_plano
Como Rodar automações web em segundo plano

## Inspirado em um video no youtubo da Hashtag Treinamentos `https://www.youtube.com/watch?v=nPNWmB7NVRU&list=WL&index=8`

Primeiro deve-se ter um código de automação web, como `Selenium`, por exemplo.

### Seguirá a codificação normal do app no `Selenium`

from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.chrome.service import Service

servico = Service(ChromeDriverManager().install())

#### Aqui começa as modificações no script
opcoes = webdriver.ChromeOptions()
opcoes.add_argument('--headless=new')
navegador = webdriver.Chrome(Service=servico, options=opcoes)
#### Fim das modicações, o script segue normalmente seu codigo

