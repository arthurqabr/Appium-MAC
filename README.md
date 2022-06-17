# Appium-MAC

## Como instalar e configurar o Appium para MAC com processador M1

### Downloads necessários:

1. Realize o Download do [Appium Desktop](https://github.com/appium/appium-desktop/releases) na última versão disponível;
2. Realize o Download do [Appium Inspector](https://github.com/appium/appium-inspector/releases) na última versão disponível;
3. Realize o Download do [Android Studio](https://developer.android.com/studio) na última versão disponível;
4. Realize o Download do [Node.js](https://nodejs.org/en/) na última versão disponível;

### Configuração:

Vamos validar se o node foi instalado corretamente. No terminal, execute os comandos:

`node -v`
e
`npm -v`

Se for exibido corretamente a versão, foi instalado com sucesso. 👍

<img width="682" alt="image" src="https://user-images.githubusercontent.com/96924797/174319278-42c790ae-8f98-4731-b00d-5b9d5f1730e7.png">

Execute o comando no terminal:

`npm install appium@latest`

Assim que finalizado, execute o comando `appium -v`

A versão do appium deverá ser exibida corretamente:

<img width="682" alt="image" src="https://user-images.githubusercontent.com/96924797/174320080-d979699a-77a9-4a27-8d75-5bc40898daeb.png">

Realize a instalação do Appium Desktop, Appium Inspector e Android Studio normalmente.

#### Agora vamos setar os caminhos necessários do Android

No terminal execute o comando:

`echo 'export PATH=$PATH:/Users/xxxxxx/automation-libs'>>~/.bash_profile`

`source ~/.bash_profile`

Agora, execute o comando: `vi ~/.bash_profile`


Seu arquivo deverá estar como este:

<img width="682" alt="image" src="https://user-images.githubusercontent.com/96924797/174321877-af91fcdb-4555-408f-9117-69db17f58ae2.png">

Caso não esteja, edite o arquivo e mantenha com essas configurações.

#### Vamos criar um device no Android Studio

Acesse o Android Studio e crie um device com a versão do Android desejada. Assim que finalizado, será exibido na lista como exemplo abaixo:

<img width="912" alt="image" src="https://user-images.githubusercontent.com/96924797/174322525-ce7c9fb7-cba7-427d-9220-6ba445a14058.png">

Inicie o emulador, aguarde carregar e, se tiver sucesso, o emulador será exibido dessa forma:

<img width="458" alt="image" src="https://user-images.githubusercontent.com/96924797/174322678-09778161-c49c-418c-a438-b18cbe8b6564.png">

Assim que criado, execute o comando:

`adb devices`

Esse comando irá exibir os dispositivos disponíveis:

<img width="682" alt="image" src="https://user-images.githubusercontent.com/96924797/174323287-7c788cd7-ddab-4fdb-97bd-aa4a645f8a77.png">

#### Ativando o "Modo Desenvolvedor" no emulador

Para ativar o Modo desenvolvedor, você deve clicar **_sete vezes_** na opção “**Número da versão**”, “**Versão da MIUI**” ou “**Número de compilação**” (depende do celular) até que a mensagem “agora você é um desenvolvedor" seja exibida. Dê um intervalo de no máximo um segundo entre um toque e outro.
