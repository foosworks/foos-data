# foos_data
Backend container for data repository

Intent is to present a RESTful interface to all data objects.

Data objects
============

Table
-----
Represents a PiFoos table, or something that can send goals and game starts to foos-collect.
```
Table: ID
Name: STRING
```

Player
------
```
Player: ID
Name: STRING
```

Match
-----
Some number of Players competing under a set of rules that determine who wins points for league placements.
```
Match: ID
League: League ID
Season: {optional}
Tournament: {optional}
Players: {list}
Rules: {object}
Start Time: DATETIME
End Time: DATETIME
Games Won Blue: NUM
Games Won Red: NUM
```

Game
----
Individual round in a match.
```
Game: ID
Match: ID
Blue Striker: Player ID
Red Striker: Player ID
Blue Goalie: Player ID
Red Goalie: Player ID
Start Time: DATETIME
End Time: DATETIME
Final Score Blue: NUM
Final Score Red: NUM
```

Goal
----
Individual scoring event in a game.
```
Game: ID
Conceded: Team ID (Goalie - Player ID)
Time: DATETIME
```

Federation
----------
A set of leagues.

Season
------
A collection of matches that determine league placement.

Tournament
----------
A collection of matches outside league placement.

League
------
A group of players that are of similar skill level.

Player League
-------------
Object linking Players and Leagues.  (depending on data structures, may not be needed?)


