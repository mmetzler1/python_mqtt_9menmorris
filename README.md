# python_mqtt_9menmorris
9 men morris over mqtt

This project is part of a school project,
which intends to play 9menmorris sending mqtt message to each play partner.
The game will be programmed in python. Data is exchanged over MQTT in JSON format.

Data in JSON format
Description of MQTT messages:

type: String = “putnew”
player: Number
x: number
y: number
coin: number
Description:
put new stone (9 white and black stones are available)
player: 1 (white)
player: 2 (black)
coin: 0..8 (optional for python game)

type: String = “pick”
player: Number
x: number
y: number
Description:
pick stone from board (to put or remove) the stone 
x: row, y: column (see picture x-y coordinates below)

type: String = “put”
player: Number
x: number
y: number
Description:
put stone to board (after pick)
x: row, y: column (see picture below)

type: String = “remove”
player: Number
x: number
y: number
Description:
remove stone from game
x: row, y: column
player: 1 (removes black stone), 
player: 2 (removes white stone)

type: String = “cleanup”
player: Number
Description:
remove all game stones on the board, so that the board is empty. (all moves since the last cleanup should be stored by the game app)

type: String = “error”
player: Number
msg: String
Description:
error message, if a command is sent, which does not apply to the game rules

