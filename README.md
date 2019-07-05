[![IBM Cloud](https://img.shields.io/badge/IBM%20Cloud-powered-blue.svg)](https://cloud.ibm.com)
[![Platform](https://img.shields.io/badge/platform-nodejs-lightgrey.svg?style=flat)](https://developer.ibm.com/node/)
[![Slack](https://maratona-inviter.mybluemix.net/badge.svg)](https://ibm.biz/convite-slack)

# Desafio 01 | Grupo Pão de Açucar

* [Desafio](#desafio)
* [Avaliação](#avaliação)
* [Tecnologias e Serviços](#tecnologias-e-serviços)
* [Treinamento no Watson Assistant](#treinamento-no-watson-assistant)
* [Deploy](#deploy)
    * [IBM Cloud](#ibm-cloud)
    * [Local](#local)
* [Submissão](#submissão)
* [Material de Apoio](#material-de-apoio)
* [Dúvidas](#dúvidas)
* [PDF do Desafio](#pdf-do-desafio)
* [License](#license)

## Desafio

O Grupo Pão de Açúcar (GPA), lançou no final de 2018 o Pão de Açúcar Adega, uma plataforma omnichannel para a venda de vinhos e outras bebidas alcoólicas, formada por um site, app e loja física com o objetivo de alavancar ainda mais a venda de vinhos através de um conceito rico em produtos selecionados, conteúdo e experiência. 

Gostaríamos de desenvolver um assistente virtual para facilitar a escolha e auxiliar o cliente na compra de um vinho. 

Espera-se que este assistente virtual seja capaz de responder dúvidas, tais como:
* Qual vinho combina mais com carnes de caça? 
* Qual vinho é adequado para bacalhau?
* Preciso de um vinho para combinar com peixe.
* Pretendo servir queijo branco como aperitivo. Qual é o vinho que melhor combina com este queijo? 
* Eu quero uma sugestão de vinho branco para acompanhar com carne vermelha.
* Tenho um vinho tinto francês Les Violettes. Que prato você sugere que eu devo fazer para acompanhar este vinho? 
* Tenho um vinho chileno Rosé Céfiro. Que prato eu devo preparar? 

Sabemos que as regras de harmonização podem ser um tanto quanto complexas. Por exemplo, existem diversos tipos de carne vermelha e para cada tipo de carne vermelha podemos ter diferentes tipos de vinhos que harmonizam melhor. No entanto, a primeira versão deste assistente virtual irá tratar apenas poucas relações de harmonização. Estas relações são apresentadas na Tabela 1. 

<div align="center">
    <img width="750" src="doc/source/images/Tabela%2001.jpg" />
    <p>Tabela 1: Regras de harmonização.</p>
</div>
<br>
<br>
<br>

Além de perguntas diretas, como as apresentadas na Tabela 1, este assistente virtual também terá que tratar perguntas de escopo aberto, como por exemplo:
* Vou dar um jantar em casa. Qual vinho devo comprar? 
* Vou servir uma massa no almoço. Qual é o vinho que melhor combina? 
* Pretendo servir queijo como aperitivo. Qual é o vinho que melhor combina? 
* Tenho um vinho tinto, que prato preparar? 

Nestes casos, o assistente virtual ao invés de retornar uma resposta direta, deverá solicitar mais informações para então fornecer uma resposta. Veja os exemplos nas Figuras 1 e 2.

<div align="center">
    <img width="375" src="doc/source/images/Figura%2001.jpg">
    <p>Figura 1: Exemplo de diálogo para perguntas abertas.</p>
</div>
<br>
<br>
<br>

<div align="center">
    <img width="375" src="doc/source/images/Figura%2002.jpg">
    <p>Figura 2: Exemplo de diálogo para perguntas abertas.</p>
</div>
<br>
<br>
<br>

Na figura 3, é apresentado uma situação onde o usuário faz uma pergunta completa logo no início do diálogo.

<div align="center">
    <img width="375" src="doc/source/images/Figura%2003.jpg">
    <p>Figura 3: Exemplo de diálogo com pergunta completa.</p>
</div>
<br>
<br>
<br>

## Avaliação

Todos os participantes da maratona deverão construir um assistente virtual sobre harmonização de vinhos como descrito acima. Para avaliar a qualidade do assistente virtual, a coordenação da maratona irá utilizar um validador automático. Por isso, é importante que no corpo de cada resposta exista uma marcação com o SKU* do vinho ou do prato recomendado. Esta marcação deve estar entre parênteses () com o número do SKU*.

Você poderá utilizar qualquer texto no corpo da resposta. No entanto, é muito importante que o texto com a marcação esteja presente. Por exemplo, uma resposta válida para a pergunta “Qual é o melhor vinho tinto para acompanhar carnes vermelhas?” é: “Sugiro um Vinho Argentino Tinto CADUS Signature Series Petit Verdot Garrafa 750ml (1178431)”. Uma resposta que não é válida para a mesma pergunta é: “Sugiro um Vinho Argentino Tinto CADUS Signature Series Petit Verdot Garrafa 750ml”.

> *O termo **Stock Keeping Unit** (**SKU**) - em português **Unidade de Manutenção de Estoque** - está ligado à logística de armazém e designa os diferentes itens do estoque, estando normalmente associado a um código identificador.

## Tecnologias e Serviços

Neste desafio você deverá resolver com o uso do seguinte serviço:

* [Watson Assistant](#treinamento-no-watson-assistant)

## Treinamento no Watson Assistant

Entre na sua conta da [IBM Cloud](https://cloud.ibm.com) e acesse o [catálogo](https://cloud.ibm.com/catalog?category=ai). Localize o serviço de [Watson Assistant](https://cloud.ibm.com/catalog/services/watson-assistant) e clique sobre ele. Você pode modificar algum dado, se quiser, como **Nome da instância** ou **Região**. Clique em "Create" para criar a instância do serviço.

Após a criação, clique em "Launch Watson Assistant" para abrir a ferramenta de treinamento.

Crie a sua *Skill* e faça o treinamento, baseado na [estória acima](#desafio). 

Para pegar as **credenciais** do serviço e do bot, procure pelo botão de três pontos, no canto superior do card. Clique em "View API Details".

<div align="center">
    <img width="430" src="doc/source/images/Watson%20Assistant%2001.png">
    <img width="430" src="doc/source/images/Watson%20Assistant%2002.png">
</div>

## Deploy

Para subir a aplicação na IBM Cloud, você consegue realizar em duas formas diferentes: via [IBM Cloud](#ibm-cloud) ou [Local](#local).

## IBM Cloud

Clique no botão abaixo e configure a aplicação pelo **Delivery Pipeline** (IBM Continuous Delivery).

[![Deploy to IBM Cloud](https://cloud.ibm.com/devops/setup/deploy/button.png)](https://cloud.ibm.com/devops/setup/deploy?repository=https://github.com/sergiogama/chatbot-D1)

## Local

Veja os pré-requisitos abaixo e siga o passo-a-passo para configurar os softwares no seu computador. Após a etapa, baixe a aplicação e configure com as credenciais para depois subir na sua conta da IBM Cloud.

### Pré-requisitos

Você deverá cumprir os seguintes itens:

- Registrar na [Maratona Behind the Code](https://ibm.biz/maratona) e confirmar o e-mail de cadastro.
- Registrar na [IBM Cloud](https://ibm.biz/BdzsFc) e confirmar o e-mail de cadastro.
- Baixar e instalar o [IBM Cloud CLI](https://cloud.ibm.com/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install_use) (usuários Mac/Linux, acesse este [link](https://cloud.ibm.com/docs/cli?topic=cloud-cli-getting-started#overview)).
- Baixar e instalar o [Git](https://git-scm.com/downloads).

Se você quiser executar a aplicação localmente, você precisará instalar:

- [Node.js](https://nodejs.org/) (de preferência a versão **LTS**).

### Login no IBM Cloud CLI

Para acessar todos os recursos na sua conta, através do comando de linha ([IBM Cloud CLI](#pré-requisitos)), você deve executar o comando abaixo em um **Terminal** (também conhecido como **Prompt** ou **Console**).

```sh
ibmcloud login
```

Como resposta, ele irá pedir seu e-mail e senha da sua conta na IBM Cloud. Forneça-os.

Após o login, você deve apontar o seu acesso local para a organização Cloud Foundry usada na IBM Cloud. Para isso, execute o comando abaixo.

```sh
ibmcloud target --cf
```

### Baixar e configurar o app

Baixe o app usando o comando do Git e acesse a pasta.

```sh
git clone git@github.ibm.com:maratonabehindthecode/desafio-1.git
cd desafio-1
```

Crie um arquivo `.env` no diretório raiz do projeto. Você pode criar normalmente este arquivo ou executar o comando abaixo (ele deve )

```sh
cp env.sample .env
```

Dentro desse arquivo `.env`, você deverá preencher com as credenciais do Watson Assistant e o seu ID da Maratona (usado no seu link para trazer novos inscritos). Preencha com os dados, após o `=` (símbolo de **igual**).

```
# Credenciais para o Desafio 1
DESAFIO=1
MARATONA_ID=

# Watson Assistant
SERVICE_ENDPOINT=https://gateway-wdc.watsonplatform.net/assistant/api
IAM_APIKEY=
WORKSPACE_ID=

```

### Subir na sua conta da IBM Cloud

Abra o arquivo `manifest.yml` e altere o `<maratona-id>` para o seu id da Maratona. Ex: id = 100001; e URL = 100001-desafio1-behindthecode.mybluemix.net. Caso você não saiba o seu id, verifique no e-mail após a sua confirmação na Maratona. **O id é necessário para a entrega e validação do seu desafio**.

Execute o comando abaixo para subir a sua aplicação na sua conta da IBM Cloud.

```sh
npm run deploy
```

ou 

```sh
ibmcloud cf push
```

Agora abra a sua aplicação no browser.

```
https://<maratona-id>-desafio1-behindthecode.mybluemix.net
```

## Submissão

Através da aplicação na IBM Cloud (`https://<maratona-id>-desafio1-behindthecode.mybluemix.net`), você irá clicar no botão **SUBMIT ASSISTANT**, preencher com o seu CPF e enviar para a avaliação final.

<div align="center">
    <img width="750" src="doc/source/images/App%2001.png">
</div>

Não iremos divulgar a nota no momento da submissão. Todos serão notificados, depois, com a sua nota no desafio.

## Material de apoio

- [O que é a IBM Cloud e como subir a sua primeira aplicação na nuvem](https://medium.com/ibmdeveloperbr/o-que-%C3%A9-a-ibm-cloud-e-como-subir-a-sua-primeira-aplica%C3%A7%C3%A3o-na-nuvem-41bfd260a2b7?source=friends_link&sk=7944d2fe14aa940e9bade68ce0731ba0)
- [Watson Assistant: Como criar o seu chatbot usando Skills e Assistants](https://medium.com/ibmdeveloperbr/watson-assistant-como-criar-o-seu-chatbot-usando-skills-e-assistants-755b4677984b?source=friends_link&sk=19bcbdb2ef573a717f63f0cc1fd4b754)
- [Code Pattern: Assemble a pizza-ordering chatbot dialog](https://developer.ibm.com/patterns/assemble-a-pizza-ordering-chatbot-dialog/)

## Dúvidas

Acesse o slack e mande a sua dúvida: [ibm.biz/convite-slack](https://ibm.biz/convite-slack).

## PDF do Desafio

> Baixe o PDF do desafio [aqui](doc/source/pdf/Storytelling.pdf).

## License

Copyright 2019 Maratona Behind the Code

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
