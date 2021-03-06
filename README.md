<img src="https://github.com/LucBerge/Datafus/raw/master/images/banner_tags.png" />

![Release](https://img.shields.io/github/workflow/status/LucBerge/Datafus/Release/master?label=release)
![Website](https://img.shields.io/github/workflow/status/LucBerge/Datafus/Website/master?label=website)
[![Release](https://img.shields.io/github/v/release/LucBerge/Datafus)](https://github.com/LucBerge/Datafus/releases)
[![License](https://img.shields.io/github/license/LucBerge/Datafus)](https://github.com/LucBerge/Datafus/blob/master/LICENSE)

# Datafus

Datafus is a small python3 tool to build the dofus database by scrapping the website. The final databases is a JSON file.

## Download the database

If you need the database in local for your project, you download it here :

- [French database](https://github.com/LucBerge/Datafus/releases/latest)
- [English database](https://github.com/LucBerge/Datafus/releases/latest)
- [German database](https://github.com/LucBerge/Datafus/releases/latest)
- [Spanish database](https://github.com/LucBerge/Datafus/releases/latest)
- [Itanian database](https://github.com/LucBerge/Datafus/releases/latest)
- [Portuguese database](https://github.com/LucBerge/Datafus/releases/latest)

## Use the RESTFULL API

If you don't need the database in local, you can use the RESTFUL API setup on GitHub pages. Simply do a get request with the following url :

- List all the items in the category :
```
https://lucberge.github.io/Datafus/{date}/{language}{category}
```
> Exemple :
> 
> Get all the monsters :
> https://lucberge.github.io/Datafus/21.01.27/fr/monsters

- Find an item from it's id :
```
https://lucberge.github.io/Datafus/{date}/{language}/{category}/{id}
```
*You need to remove the `s` in the `category` value.*

> Exemple :
> 
> Get the monsters with a specific id:
> https://lucberge.github.io/Datafus/21.01.27/fr/monster/1047

## File structure

- `monsters`  **_List of Item_**: List of monsters in the game
- `weapons` **_List of Item_**: List of weapons in the game
- `equipments` **_List of Item_**: List of equipments in the game
- `sets` **_List of Item_**: List of sets in the game
- `pets` **_List of Item_**: List of pets in the game
- `mounts` **_List of Item_**: List of mounts in the game
- `consumables` **_List of Item_**: List of consumables in the game
- `resources` **_List of Item_**: List of resources in the game
- `ceremonial_items` **_List of Item_**: List of ceremonial items in the game
- `sidekicks` **_List of Item_**: List of sidekicks items in the game
- `idols` **_List of Item_**: List of idols in the game
- `harnesses` **_List of Item_**: List of harnesses in the game

## Item structure

The following table show the feilds which exists or not for a given item.

✔️ The field is mandatory

⚫ The field is optionnal

❌ The field doesn't exists


|Field                 | Monster | Weapon | Equipment | Set | Pet | Mount | Consumable | Resource | Cremonial item | Sidekick | Idol | Harnesse |
|----------------------|:-------:|:------:|:---------:|:---:|:---:|:-----:|:----------:|:--------:|:--------------:|:--------:|:----:|:--------:|
|`url` **key**         |✔️       |✔️       |✔️          |✔️   |✔️    |✔️      |✔️          |✔️         |✔️               |✔️        |✔️     |✔️         |
|`id`                  |✔️       |✔️       |✔️          |✔️   |✔️    |✔️      |✔️          |✔️         |✔️               |✔️        |✔️     |✔️         |
|`name`                |✔️       |✔️       |✔️          |✔️   |✔️    |✔️      |✔️          |✔️         |✔️               |✔️        |✔️     |✔️         |
|`img`                 |✔️       |✔️       |✔️          |✔️   |✔️    |✔️      |✔️          |✔️         |✔️               |✔️        |✔️     |✔️         |
|`type`                |✔️       |✔️       |✔️          |✔️   |✔️    |✔️      |✔️          |✔️         |✔️               |✔️        |✔️     |✔️         |
|`level`               |✔️       |✔️       |✔️          |✔️   |✔️    |❌     |✔️           |✔️         |✔️               |❌       |✔️     |✔️         |
|`description`         |❌       |✔️       |✔️          |❌   |✔️    |❌     |✔️          |✔️         |✔️               |✔️        |✔️     |✔️         |
|`effects`             |❌       |⚫       |⚫          |❌   |❌    |⚫     |⚫         |⚫         |⚫               |❌        |❌     |❌        |
|`conditions`          |❌       |⚫       |⚫          |❌   |❌    |❌     |⚫         |⚫         |⚫               |❌        |❌     |⚫        |
|`characteristics`     |✔️       |✔️       |❌          |❌   |❌    |✔️     |❌          |❌        |⚫               |✔️        |❌     |❌        |
|`resistances`         |✔️       |❌       |❌          |❌   |❌    |❌     |❌         |❌         |❌              |❌        |❌     |❌        |
|`craft`               |❌       |⚫       |⚫          |❌   |❌    |❌     |⚫         |⚫         |⚫               |❌        |✔️     |⚫        |
|`bonuses`             |❌       |❌       |❌          |❌   |❌    |❌     |❌         |❌         |❌              |❌        |✔️     |❌        |
|`items`               |❌       |❌       |❌          |✔️   |❌    |❌     |❌         |❌         |❌              |❌        |❌     |❌        |
|`set_bonuses`         |❌       |❌       |❌          |✔️   |❌    |❌     |❌         |❌         |❌              |❌        |❌     |❌        |
|`set_total_bonuses`   |❌       |❌       |❌          |⚫   |❌    |❌     |❌         |❌         |❌              |❌        |❌     |❌        |
|`evolutionary_effects`|❌       |❌       |❌          |❌   |⚫    |❌     |❌         |❌         |❌              |❌        |❌     |❌        |
|`spells`              |❌       |❌       |❌          |❌   |❌    |❌     |❌        |❌          |❌              |❌        |✔️     |❌        |

## Fields description

- `url` **_String_**: Url of the item. **Unique for each item.**
```json
"url":...
```

- `id` **_Integer_**: Id of the item.
```json
"id":...
```

- `name` **_String_**: Name of the item.
```json
"name":...
```

- `img` **_String_**: Image url of the item.
```json
"img":...
```

- `type` **_String_**: Type of the item (Bow, Cereal, Ore, Beer...)
```json
"type":...
```

- `level` **_Integer_ (Monsters exclude)**: Level of the item from 1 to 200.
```json
"level":...
```

- `level` **_Tuple of Integer_ (Monsters only)**: Minimal and Maximal value of the monster from 1 to 200.
```json
"level":[
  ...,
  ...
]
```

- `description`  **_String_**: Description of the item.
```json
"description":...
```

- `effects` **_List of String_** : List of string effects.
```json
"effects":[
  ...,
  ...
]
```

- `conditions` **_List of String_** : List of string conditions.
```json
"conditions":[
  ...,
  ...
]
```

- `characteristics` **_List of String_**: List of string characteristics.
```json
"characteristics":[
  ...,
  ...
]
```

- `resistances` **_List of String_**: List of string resistances.
```json
"resistances":[
  ...,
  ...
]
```

- `craft` **_List of Craft_** : How to craft the item.
```json
"craft":[
  {
    "url":...,
    "quantity":...
  },
  {
    "url":...,
    "quantity":...
  },
  ...
]
```

- `bonuses` **_List of String_**: List of string bonuses.
```json
"bonuses":[
  ...,
  ...
]
```

- `items` **_List of String_**: List of items url.
```json
"items":[
  ...,
  ...
]
```

- `set_bonuses` **_List of String_**: List of string set bonuses.
```json
"set_bonuses":[
  ...,
  ...
]
```

- `set_total_bonuses` **_List of String_** : List of string set total bonuses.
```json
"set_total_bonuses":[
  ...,
  ...
]
```

- `evolutionary_effects` **_List of String_** : List of string evolutionary effects.
```json
"evolutionary_effects":[
  ...,
  ...
]
```

- `spells` **_List of String_**: List of string spells.
```json
"spells":[
  ...,
  ...
]
```
