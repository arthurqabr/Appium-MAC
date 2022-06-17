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

> Altere "xxxxx" para seu usuário.

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

#### Abrindo o Appium

Inicie o Appium Desktop e o que deverá ser exibido é uma tela como abaixo:

<img width="762" alt="image" src="https://user-images.githubusercontent.com/96924797/174327788-adf0373e-88ac-4ce6-bf5c-b829467d14e9.png">

Vamos fazer as primeiras configurações:

1. Acesse a aba "Advanced" e defina os valores:
   - Server Address: `localhost`
   - Server Port: `4723`
   - Allow CORS: `Ative`

Os outros parâmetros, mantenha como está.

Agora acesse "Edite configurations ⚙️":

Informe os caminhos abaixo:

ANDROID_HOME: `/Users/xxxxxx/Library/Android/sdk`

JAVA_HOME: `/Library/Java/JavaVirtualMachines/jdk1.8.0_241.jdk/Contents/Home/bin:$PATH`

> Lembrando que 'xxxxx' é o seu usuário.

**DICA: Salve este preset para não precisar preencher cada vez que iniciar o Appium 😜**

Inicie o servidor. Será exibida uma tela como essa:

<img width="762" alt="image" src="https://user-images.githubusercontent.com/96924797/174329633-f734172e-bea4-473a-a337-6c53c66d6d5b.png">

#### Abrindo o Appium Inspector

Abra o Appium Inspector e parametrize da seguinte forma:
  - Remote Host: `localhost`
  - Remote Port: `4723`
  - Remote Path: `/wd/hub`

Em "Desired Capabilities" preencha:
  - platformName   | text | Android
  - automationName | text | UiAutomator2
  - udid           | text | Aqui deverá preencher com o ID que encontramos com o comando `adb devices`. No meu caso é o "emulator-5554"
  - app            | text | É o caminho do seu aplicativo, incluindo a extensão dele.

> Para ver outras capabilities disponíveis, [clique aqui](https://github.com/appium/appium/blob/master/docs/en/writing-running-appium/caps.md)

Marque a opção: "✅ Automatically add necessary Appium vendor prefixes on start"

Ficará como o exemplo abaixo:

<img width="1392" alt="image" src="https://user-images.githubusercontent.com/96924797/174330432-544145a6-ae12-4ed7-b8e6-733b8fbd6328.png">

**DICA: Salve este preset também! 🙂**

Clique em "Start Session". Se a tela exibida for como a tela abaixo, seu Appium foi configurado com sucesso! 🥳

<img width="1392" alt="image" src="https://user-images.githubusercontent.com/96924797/174331374-a7c21ad4-6597-462c-9497-af5572de6922.png">
