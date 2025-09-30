![Banner do Mod](https://github.com/zerodawnbr/zerodawntoolbox/blob/main/imgs/zerodawntoolbox2.jpg)

# 🎁 Kit de Boas-Vindas

O **Kit de Boas-Vindas** é um recurso que entrega itens iniciais para o jogador quando ele entra no servidor pela primeira vez.  
Ele foi criado para facilitar o início da jornada e tornar a experiência mais divertida.

Necessário ter o MOD @CF instalado
---

## 📂 Arquivo de configuração

Ao iniciar o servidor pela primeira vez, é criado automaticamente o arquivo de configuração.

**Se estiver com o mod ToolBox**

`$profile:/ZeroDawnBRCoreTools/WelcomeKit/Config.json`

**Se estiver apenas com o mod KitBoasVindas**

`$profile:/ZeroDawnBRKit/Config.json`


---

## ⚙️ Funcionalidades

- **Itens configuráveis**  
  Qualquer item listado no `types.xml` pode ser adicionado ao kit.

- **Local de spawn**  
  Escolha se os itens aparecem **direto no inventário** do jogador ou **fora dele**, dentro de um contêiner (ex.: caixa).

- **Itens aleatórios**  
  Defina uma porcentagem de chance para spawnar itens aleatórios.  
  Exemplo: `randomItemPercentage = 50` → 50% de chance de receber o item.

- **Sistema VIP**  
  Permite configurar kits exclusivos para jogadores VIP com base no **SteamID**.  
  Cada grupo (Gold, Silver, Bronze) pode ter itens diferentes.

## 💡 Importante
  Para alguns servidores, o uso da barra (\\) no atributo ***keywords*** para definir as palavras chaves não funciona, você pode usar outro caractere como **!** ou **-**, ou até mesmo deixar apenas a palavra. Mas cuidado com a palavra que usar para não atrapalhar as mensagens do chat.

---

## Arquivo json
```json
{
    "version": "1.0.1",
    "info": "This file defines which items the player will receive. VIP players will receive additional items as part of the benefit.",
    "container": "WoodenCrate",
    "spawnInventory": 0,
    "message1": "Welcome, Here's your starter kit.",
    "licensedTo": "Licensed To",
    "serverIP": "servidor:porta",
    "serverName": "Server Name",
    "serverNo": "1",
    "randomItemPercentage": 100,
    "items": [
        {
            "classType": "Apple",
            "quantity": 1,
            "attachments": []
        },
        {
            "classType": "Plum",
            "quantity": 1,
            "attachments": []
        },
        {
            "classType": "Candycane_RedGreen",
            "quantity": 1,
            "attachments": []
        },
        {
            "classType": "Rope",
            "quantity": 1,
            "attachments": []
        },
        {
            "classType": "Shovel",
            "quantity": 1,
            "attachments": []
        },
        {
            "classType": "BBP_Blueprint",
            "quantity": 1,
            "attachments": []
        },
        {
            "classType": "TerritoryFlagKit",
            "quantity": 1,
            "attachments": []
        }
    ],
    "keywords": [
        "!kit",
        "kit",
        "\\kit",
        "\\welcomepack",
        "\\welcomekit",
        "\\boasvindas",
        "!boasvindas",
        "boasvindas"
    ],
    "vips": {
        "Gold": {
            "steamids": [
                "76561198000000001",
                "76561198000000002"
            ],
            "items": [
                {
                    "classType": "M4A1",
                    "quantity": 1,
                    "attachments": [
                        "Mag_STANAG_30Rnd",
                        "GhillieAtt_Black",
                        "M4_CarryHandleOptic",
                        "UniversalLight",
                        "M4_OEBttstck_Black",
                        "M9A1_Bayonet",
                        "M4_Suppressor",
                        "Battery9V"
                    ]
                },
                {
                    "classType": "Ammo_556x45",
                    "quantity": 1,
                    "attachments": []
                }
            ]
        },
        "Silver": {
            "steamids": [
                "76561198000000003",
                "76561198000000004"
            ],
            "items": [
                {
                    "classType": "SKS",
                    "quantity": 1,
                    "attachments": [
                         "GhillieAtt_Tan",
                         "SKS_Bayonet",
                         "ImprovisedSuppressor",
                         "Mag_CLIP762x39_10Rnd",
                         "PUScopeOptic",
                         "Battery9V"
            ]
                },
                {
                    "classType": "Ammo_762x39",
                    "quantity": 1,
                    "attachments": []
                }
            ]
        },
        "Bronze": {
            "steamids": [
                "76561198000000005"
            ],
            "items": [
                {
                    "classType": "Shotgun",
                    "quantity": 1,
                    "attachments": []
                },
                {
                    "classType": "Ammo_12gaPellets",
                    "quantity": 1,
                    "attachments": []
                }
            ]
        }
    }
}
```

## 💡 Resumindo

Esse mod funciona como um **starter pack** automático:  
- Ajuda novos jogadores a começarem equipados.  
- Entrega kits básicos para todos.  
- Oferece vantagens extras para jogadores VIP.  
- 100% configurável pelo `Config.json`.  

![alt](https://github.com/zerodawnbr/zerodawntoolbox/blob/main/imgs/kitboasvindasmochila.png)

# 🎁 Explicação dos campos – WelcomeKit

## Seção principal (`config.json`)

| Campo                | Descrição                                                                                 | Valor Padrão / Exemplo |
|-----------------------|-------------------------------------------------------------------------------------------|-------------------------|
| `version`             | Versão do sistema de Welcome Kit.                                                         | `"1.0.1"`              |
| `info`               | Texto informativo/descritivo do sistema.                                                   | `"This file defines which items the player will receive..."` |
| `container`          | Define o contêiner usado para entregar os itens. Pode ser caixa, barril, baú, etc.              | `"WoodenCrate"`         |
| `spawnInventory`  | Define onde os itens serão spawnados: <br> `1` = no inventário do jogador <br> `0` = fora, em um container. | `0` |
| `message1`           | Mensagem exibida ao jogador ao receber o kit.                                              | `"Welcome, Here's your starter kit."` |
| `randomItemPercentage` | Chance percentual de um item aleatório ser incluído no kit.                              | `100` (sempre recebe todos) |
| `items[]`            | Lista de itens básicos que todos jogadores recebem (classe e quantidade).                  | `[{"classType": "Apple","quantity": 1}, ...]` |
| `keywords[]`     | Lista de comandos (chat) que o jogador pode digitar para receber o kit.                    | `["\\kit", "\\welcomepack", "\\welcomekit", "\\boasvindas"]` |

---

## Estrutura dos `items`

| Campo        | Descrição                                               | Exemplo |
|--------------|---------------------------------------------------------|---------|
| `classType`  | Nome do item conforme registrado no `types.xml`.        | `"Apple"` |
| `quantity`   | Quantidade do item a ser entregue.                      | `1`       |
| `attachments`| Permite anexar itens ao item principal.                 |          |

---

## Seção: `vips`

Sistema que permite **grupos de jogadores VIP** receberem kits diferenciados.  
Cada nível (Gold, Silver, Bronze, etc.) pode ter **SteamIDs vinculados** e uma lista de itens próprios.

| Campo            | Descrição                                                                 | Exemplo |
|------------------|---------------------------------------------------------------------------|---------|
| `Gold` / `Silver` / `Bronze` | Categoria de VIP (pode ser personalizada).                       | `"Gold"` |
| `steamids[]`     | Lista de SteamIDs que pertencem ao grupo VIP.                             | `["76561198000000001","76561198000000002"]` |
| `items[]`        | Itens extras que somente jogadores desse grupo receberão.                 | `[{"classType":"M4A1","quantity":1,"attachments": []},{"classType":"Ammo_556x45","quantity":1,"attachments": []}]` |

---

## Estrutura dos `vips.items`

| Campo        | Descrição                                        | Exemplo |
|--------------|--------------------------------------------------|---------|
| `classType`  | Nome do item exclusivo do VIP.                   | `"M4A1"` |
| `quantity`   | Quantidade do item VIP a ser entregue.           | `1`      |
| `attachments`| Permite anexar itens ao item principal.          |          |

## 📜 Registro de Kits Entregues

Quando um jogador recebe o **Kit de Boas-Vindas**, o sistema cria automaticamente um arquivo chamado: $profile:/ZeroDawnBRCoreTools/WelcomeKit/welcomekit.json


Esse arquivo registra **quem já recebeu o kit** e os itens entregues, garantindo que o jogador **não possa receber novamente**.

---

## 🗂️ Estrutura do `welcomekit.json`

```json
{
    "76561198000000000": {
        "userName": "player1",
        "steamID": "76561198868988100",
        "date": "2025-9-24 22:24:56",
        "items": [
            {
                "classType": "AmmoBox_12gaSlug_10Rnd",
                "quantity": 1,
                "attachments": []
            },
            {
                "classType": "Apple",
                "quantity": 1,
                "attachments": []
            },
            {
                "classType": "Plum",
                "quantity": 1,
                "attachments": []
            },
            {
                "classType": "SodaCan_Cola",
                "quantity": 1,
                "attachments": []
            },
            {
                "classType": "Candycane_RedGreen",
                "quantity": 1,
                "attachments": []
            },
            {
                "classType": "Rope",
                "quantity": 1,
                "attachments": []
            },
            {
                "classType": "Shovel",
                "quantity": 1,
                "attachments": []
            },
            {
                "classType": "Whetstone",
                "quantity": 1,
                "attachments": []
            },
            {
                "classType": "SKS",
                "quantity": 1,
                "attachments": [
                    "GhillieAtt_Tan",
                    "SKS_Bayonet",
                    "ImprovisedSuppressor",
                    "Mag_CLIP762x39_10Rnd",
                    "PUScopeOptic",
                    "Battery9V"
                ]
            },
            {
                "classType": "M4A1",
                "quantity": 1,
                "attachments": [
                    "Mag_STANAG_30Rnd",
                    "GhillieAtt_Black",
                    "M4_CarryHandleOptic",
                    "UniversalLight",
                    "M4_OEBttstck_Black",
                    "M9A1_Bayonet",
                    "M4_Suppressor",
                    "Battery9V"
                ]
            },
            {
                "classType": "NVGHeadstrap",
                "quantity": 1,
                "attachments": [
                    "NVGoggles",
                    "Battery9V"
                ]
            }
        ]
    }
}
```

## 📖 Explicação dos campos – welcomekit.json

| Campo       | Descrição                                                                 | Exemplo                          |
|-------------|---------------------------------------------------------------------------|----------------------------------|
| `steamID`   | Identificador único do jogador na Steam. Serve como chave do registro.    | `"76561198868988100"`            |
| `userName`      | Nome do jogador no momento em que recebeu o kit.                          | `"player1"`                      |
| `date`      | Data e hora em que o kit foi entregue ao jogador.                         | `"2025-8-24 16:21:40"`           |
| `items[]`   | Lista de itens que foram entregues ao jogador.                            | `["Apple","Plum","SodaCan_Cola","Candycane_RedGreen","Rope"]` |

## 💡 Atenção
- Dependendo da quantidade de itens a serem entregues, é preciso incluir um container maior, caso contrario não será entregue ao jogador
- Se incluir uma mochila no atributo **container** e definir **spawnInventory** como 1. A mochila será colocada nas costas do jogador (desde que não haja outra).
- Quando usar mochilas, as armas irão automaticamente para o slot de armas quando houver, se incluir mais uma arma e não tiver slot, será guardado dentro da mochila caso tenha espaço.

## 📂 Atualização
09-09-2025
- Tradução para 12 idiomas
- Ajustes na configuração dos itens para usuários VIP's

24-09-2025
- Ajuste de anexos para armas e equipamentos
