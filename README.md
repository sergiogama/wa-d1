[![IBM Cloud](https://img.shields.io/badge/IBM%20Cloud-powered-blue.svg)](https://cloud.ibm.com)
[![Platform](https://img.shields.io/badge/platform-nodejs-lightgrey.svg?style=flat)](https://developer.ibm.com/node/)
[![Slack](https://maratona-inviter.mybluemix.net/badge.svg)](https://ibm.biz/convite-slack)

## IBM Cloud

Clique no botão abaixo e configure a aplicação pelo **Delivery Pipeline** (IBM Continuous Delivery).

[![Deploy to IBM Cloud](https://cloud.ibm.com/devops/setup/deploy/button.png)](https://cloud.ibm.com/devops/setup/deploy?repository=https://github.com/sergiogama/wa-d1)

## Local

Veja os pré-requisitos abaixo e siga o passo-a-passo para configurar os softwares no seu computador. Após a etapa, baixe a aplicação e configure com as credenciais para depois subir na sua conta da IBM Cloud.

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
```

