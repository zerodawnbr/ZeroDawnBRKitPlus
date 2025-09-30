![Banner do Mod](https://github.com/zerodawnbr/zerodawntoolbox/blob/main/imgs/zerodawntoolbox2.jpg)

# 🎁 Kit de Boas-Vindas Plus

O **Kit de Boas-Vindas Plus** é uma versão aprimorada do kit já existente. Ele não funciona em conjunto com o kit padrão, mas sim como uma alternativa com recursos adicionais.

Assim como o kit original, ele concede itens iniciais ao jogador na sua primeira entrada no servidor, ajudando a tornar o começo da jornada mais fácil e divertido. A diferença é que esta versão traz novas funcionalidades: você pode enviar kits para todos os jogadores de uma vez ou definir grupos específicos que receberão determinados kits.

Para utilizá-lo é necessário ter o **MOD @CF** instalado.

O **[Kit de Boas-Vindas](https://github.com/zerodawnbr/zerodawntoolbox/wiki/Kit-Boas-Vindas)** e o **Kit de Boas-Vindas Plus** possuem objetivos semelhantes, mas cada um tem características próprias.

---

## 📂 Arquivo de configuração

Ao iniciar o servidor pela primeira vez, é criado automaticamente o arquivo de configuração.

**Se estiver com o mod ToolBox**

`$profile:/ZeroDawnBRCoreTools/WelcomeKit/Config.json`

**Se estiver apenas com o mod KitBoasVindas**

`$profile:/ZeroDawnBRKitPlus/Config.json`


---

## ⚙️ Funcionalidades

- **Itens configuráveis**  
  Qualquer item listado no `types.xml` pode ser adicionado ao kit.

- **Local de spawn**  
  Escolha se os itens aparecem **direto no inventário** do jogador ou **fora dele**, dentro de um contêiner (ex.: caixa).

- **Itens aleatórios**  
  Defina uma porcentagem de chance para spawnar itens aleatórios.  

- **Criação de vários kits**  
  Permite criar vários kits que poderão ser entregues aos jogadores. Porém apenas 1 kit será entregue, evitando o jogador receber o mesmo kit várias vezes.

- **Kit específicos**  
  Usando o steamID do jogador, você pode definir kits especificos para eles.

## 💡 Importante
  Para alguns servidores, o uso da barra (\\) no atributo ***kits*** para definir as palavras chaves não funciona, você pode usar outro caractere como **!** ou **-**, ou até mesmo deixar apenas a palavra. Mas cuidado com a palavra que usar para não atrapalhar as mensagens do chat.

---

## Arquivo json
```json
{
    "versao": "1.0.0",
    "info": "The Welcome Kit is a feature that delivers starter items to the player when they first join the server.",
    "spawnInventory": 0,
    "message1": "Entrega de kit.",
    "message2": "O seu kit foi entregue.",
    "message3": "Você já recebeu o seu kit!",
    "NotificationInChat": 1,
    "kits": {
        "\\kitexemplo1": {
            "container": "WoodenCrate",
            "items": [
                {
                    "classType": "Apple",
                    "quantityMax": 1,
                    "health": 1.0,
                    "chance": 1.0,
                    "attachments": []
                }
            ],
            "steamID": [
                    "00000000000000000000",
                    "00000000000000000001"
            ]
        },
        {
        "\\kitexemplo2": {
            "container": "SeaChest",
            "items": [
                {
                    "classType": "Plum",
                    "quantityMax": 2,
                    "health": 1.0,
                    "chance": 0.5,
                    "attachments": []
                }
            ],
            "steamID": []
        }
    }
}
```

## 💡 Resumindo

- Ajuda novos jogadores a começarem equipados.  
- Entrega kits básicos para todos.  
- Permite distribuir varios kits para o mesmo jogador.
- Distribui apenas um vez o kit, evitando assim que o jogador receba o mesmo kit várias vezes.
- 100% configurável pelo `Config.json`.  

![alt](https://github.com/zerodawnbr/zerodawntoolbox/blob/main/imgs/kitboasvindasmochila.png)

# 🎁 Explicação dos campos – WelcomeKit

## Seção principal (`config.json`)

| Atributo                | Descrição                                                                                 | Valor Padrão / Exemplo |
|-----------------------|-------------------------------------------------------------------------------------------|-------------------------|
| `version`             | Versão do sistema de Welcome Kit.                                                         | `"1.0.1"`              |
| `info`                | Texto informativo/descritivo do sistema.                                                   | `"This file defines which items the player will receive..."` |
| `message1`            | Mensagem exibida ao jogador ao receber o kit.                                              | `"Você está recebendo o seu kit"` |
| `message1`            | Mensagem exibida ao jogador ao receber o kit.                                              | `"O kit foi entregue"` |
| `message1`            | Mensagem exibida ao jogador ao receber o kit.                                              | `"Você já recebeu o seu pacote. Você só pode solicitar uma vez por temporada."` |
| `spawnInventory`      | Define onde os itens serão spawnados: <br> `1` = no inventário do jogador <br> `0` = fora, em um container. | `0` |
| `NotificationInChat`  | Notificação no chat do jogo: <br> `1` = exibe <br> `0` = oculta. | `0` |

---

## Estrutura dos `kits`

| Atributo        | Descrição                                               | Exemplo |
|--------------|---------------------------------------------------------|---------|
| `nome do kit`| Você pode definir um nome qualquer para o kit.          | `\kitarmas` <br> `\kitsaude` <br>  etc...         |
| `container`  | Define o contêiner usado para entregar os itens. Pode ser caixa, barril, baú, etc.              | `"WoodenCrate"`         |
| `items`      | itens que serão entregues             | `[ ]`     |
| `steamID`    | Steam ID de jogadores que receberão, caso esteja em branco, liberado para todos.             | `[ ]`     |

## Estrutura dos `itens`

| Atributo        | Descrição                                               | Exemplo |
|--------------|---------------------------------------------------------|---------|
| `classType`  | Nome do item conforme registrado no `types.xml`.        | `"Apple"` |
| `quantityMax`   | Quantidade do item a ser entregue.                      | `1`       |
| `health`   | Saúde do item a ser entregue. 1 = 100%, 0.7 = 70%, etc...                     | `1.0`       |
| `chance`   | Chance do item a ser entregue. 1 = 100%, 0.7 = 70%, etc...                     | `1.0`       |
| `attachments`| Permite anexar itens ao item principal.                 | `[ ]`      |

---

## 📜 Registro de Kits Entregues

Quando um jogador recebe o **Kit de Boas-Vindas**, o sistema cria automaticamente um arquivo chamado: **welcomekit_players.json**

**Se estiver com o mod ToolBox**

`$profile:/ZeroDawnBRCoreTools/WelcomeKit/welcomekit_players.json`

**Se estiver apenas com o mod KitBoasVindas**

`$profile:/ZeroDawnBRKitPlus/welcomekit_players.json`

Esse arquivo registra **quem já recebeu o kit** e os kits que foram entregues, garantindo que o jogador **não possa receber novamente**.

---

## 🗂️ Estrutura do `welcomekit_players.json`

```json
{
    "76561198000000001": {
        "userName": "Survivor1",
        "steamID": "76561198000000001",
        "date": "2025-9-30 5:38:25",
        "claimedKits": [
            "\\kitsaude",
            "\\kitcomida",
            "\\kitarmas",
            "\\kitbase"
        ]
    },
    "76561198000000002": {
        "userName": "Survivor2",
        "steamID": "76561198000000002",
        "date": "2025-9-30 5:38:25",
        "claimedKits": [
            "\\kitsaude",
            "\\kitcomida",
            "\\kitarmas",
            "\\kitbase"
        ]
    }
}
```

## 📖 Explicação dos campos – welcomekit.json

| Atributo       | Descrição                                                                 | Exemplo                          |
|-------------|---------------------------------------------------------------------------|----------------------------------|
| `userName`      | Nome do jogador no momento em que recebeu o kit.                          | `"player1"`                      |
| `steamID`   | Identificador único do jogador na Steam. Serve como chave do registro.    | `"76561198868988100"`            |
| `date`      | Data e hora em que o kit foi entregue ao jogador.                         | `"2025-8-24 16:21:40"`           |
| `claimedKits[]`   | Lista de kits que foram entregues ao jogador.                            | `\\kitsaude` <br> `\\kitcomida` |

## 💡 Atenção
- Dependendo da quantidade de itens a serem entregues, é preciso incluir um container maior, caso contrario não será entregue ao jogador
- Se incluir uma mochila no atributo **container** e definir **spawnInventory** como 1. A mochila será colocada nas costas do jogador (desde que não haja outra).
- Quando usar mochilas, as armas irão automaticamente para o slot de armas quando houver, se incluir mais uma arma e não tiver slot, será guardado dentro da mochila caso tenha espaço.

## 📜 Registros de logs

![alt](https://github.com/zerodawnbr/zerodawntoolbox/blob/main/imgs/scriptdayzkitboasvindas.png)

## 💡 Personalização
- Caso precise, personalizamos o MOD conforme a sua necessidade.

## 🎮 Oficina na Steam
[Oficina Zero Dawn](https://steamcommunity.com/id/R0dr1g0_DEV/myworkshopfiles/?appid=221100)

## 📂 Atualizações
