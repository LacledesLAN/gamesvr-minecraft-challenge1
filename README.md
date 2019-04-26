# Laclede's LAN Minecraft Challenge 1

Minecraft world divided into multiple identical zones that are blocked off from each other. A build challenge is set and teams of 1 to 3 players gets assigned a zone. At the end each team's creation is judged.

Each zone has goodies, supplies, and [Easter-eggs](https://en.wikipedia.org/wiki/Easter_egg_(media)) spread throughout to encourage exploration. All players new to the server spawn in a 'spawn jail' which they cannot escape - an admin must teleport them to the appropriate zone.

![alt text](https://raw.githubusercontent.com/LacledesLAN/gamesvr-minecraft-challenge1/master/.docs/OverheadMap.png "Overhead Map")

## Teleportation Coordinates

### Spawn Jail

-189, 53, -141

### Islands

| Island | Spawn Room    | Front Door    | Mid Air       |
| ------ | ------------- | --------------| ------------- |
| 1      | -1067 57 -383 | -1057 64 -364 | -1099 83 -360 |
| 2      | -763 57 -383  | -753 64 -364  | -795  83 -360 |
| 3      | -459 57 -383  | -449 64 -364  | -491  83 -360 |
| 4      | -1067 57 -111 | -1057 64 -92  | -1099 83 -88  |
| 5      | -763 57 -111  | -753 64 -92   | -795  83 -88  |
| 6      | -459 57 -111  | -449 64 -92   | -491  83 -88  |
| 7      | -1067 57 160  | -1057 64 179  | -1099 83 183  |
| 8      | -763 57 160   | -753 64 179   | -795  83 183  |
| 9      | -459 57 160   | -449 64 179   | -491  83 183  |

## Admin Commands

| Description             | Command                                          | Notes |
| ----------------------- | ------------------------------------------------ | ----- |
| Enable whitelist        | `/whitelist on`                                  | Prevents players besides OP and players listed on the whitelist form connecting. Use while judging results. |
| Teleport to player      | `tp [target player] <destination player>`        |       |
| Teleport to coordinates | `tp [target player] <x> <y> <z> [<yaw> <pitch>]` |       |
| Set world spawn         | `/setworldspawn`; `/setworldspawn <x> <y> <z>`   |       |
| Set player spawn        | `/spawnpoint <player> <x> <y> <z>`               |       |
| Set game rules          | `/gamerule <rule name> [value]`                  |       |
| Night vision            | `/effect @p minecraft:night_vision 99999 255`    |       |
| Reset vision            | `/effect @p clear`                               |       |
| Give barrier block      | `/give <player> minecraft:barrier`               |       |

## Docker

### Build

```shell
docker build -t lacledeslan/gamesvr-minecraft-challenge1 -f linux.Dockerfile .
```

### Run Interactive Server

```shell
docker run -d --rm -p 25565:25565 lacledeslan/gamesvr-minecraft-challenge1 java -Xms512M -Xmx1024M -jar /app/minecraft-server.jar nogui
```
