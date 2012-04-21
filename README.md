# FIFA Ultimate Team Player Statistics

FIFA Ultimate Team exposes all player data via publicly accessible web services. This repository is here to help you build *your* ultimate team. Want to know who the tallest player is, the fastest, the best overall?

You can use this information to [hack player data](http://www.youtube.com/watch?v=vslVG-oIhcc) too, but don't do that!

## Player Images

Every player in the game has a unique identifier. Identifiers remain the same regardless of the season.

Let's take Maurice Edu as an example. He's an American midfielder currently playing for Rangers FC, the most successful club in the world. Maurice was on the cover of the American version of FIFA 11. He's also my 4-year old son's favorite player.

Mo's FIFA player ID is 179686, so we can grab his image from the 2012, 2011 and 2010 data set with the following URLs:

```
http://cdn.content.easports.com/fifa/fltOnlineAssets/2012/fut/items/images/players/web/179686.png
http://cdn.content.easports.com/fifa/fltOnlineAssets/2011/fut/items/images/players/web/179686.png
http://cdn.content.easports.com/fifa/fltOnlineAssets/2010/fut/items/images/players/web/179686.png
```

![](http://i.imgur.com/D9pTc.png)
![](http://i.imgur.com/Qph7i.png)
![](http://i.imgur.com/W6n3n.png)


## Player data

Player data is sent to the client (FIFA ultimate team on your XBOX, PS3, PC, or browser) in JSON e.g.

`http://cdn.content.easports.com/fifa/fltOnlineAssets/2012/fut/items/web/179686.json`

```javascript
{
  "Player": {
    "FirstName": "Maurice",
    "LastName": "Edu",
    "CommonName": null,
    "Height": "183",
    "DateOfBirth": {
      "Year": "1986",
      "Month": "4",
      "Day": "18"
    },
    "PreferredFoot": "Right",
    "ClubId": "86",
    "LeagueId": "50",
    "NationId": "95",
    "Rating": "66",
    "Attribute1": "79",
    "Attribute2": "61",
    "Attribute3": "64",
    "Attribute4": "67",
    "Attribute5": "67",
    "Attribute6": "78",
    "Rare": "0",
    "ItemType": "PlayerM"
  }
}
```

Most of these fields are self-explanatory, but they're detailed below:

* **Attribute1:** pace for outfield players; diving for goalkeepers
* **Attribute2:** shooting for outfield players; handling for  goalkeepers
* **Attribute3:** passing for outfield players; kicking for goalkeepers
* **Attribute4:** dribbling for outfield players; ref for goalkeepers
* **Attribute5:** defending for outfield players; speed for goalkeepers
* **Attribute6:** heading for outfield players; positioning for goalkeepers
* **Rare:** No longer used
* **ItemType:** This tells us whether the player's a goalkeeper (PlayerGk), defender (PlayerD), midfielder (PlayerM), or an attacking player (PlayerA).


## Kits

### Home

![](http://cdn.content.easports.com/fifa/fltOnlineAssets/2012/fut/items/images/kits/web/j0_00086.png)

`http://cdn.content.easports.com/fifa/fltOnlineAssets/2012/fut/items/web/6300263.json`

```
{
  "Kit": {
    "ClubId": "86",
    "LeagueId": "50",
    "NationId": "42",
    "Rating": "73",
    "Rare": "1",
    "Category": "2",
    "Desc": "TeamName_Abbr15_86",
    "BioDesc": "Rangers",
    "ItemType": "Kit"
  }
}
```

### Away

![](http://cdn.content.easports.com/fifa/fltOnlineAssets/2012/fut/items/images/kits/web/j1_00086.png)

`http://cdn.content.easports.com/fifa/fltOnlineAssets/2012/fut/items/web/6400263.json`


```
{
  "Kit": {
    "ClubId": "86",
    "LeagueId": "50",
    "NationId": "42",
    "Rating": "73",
    "Rare": "1",
    "Category": "3",
    "Desc": "TeamName_Abbr15_86",
    "BioDesc": "Rangers",
    "ItemType": "Kit"
  }
}
```

## Badges

![](http://cdn.content.easports.com/fifa/fltOnlineAssets/2012/fut/items/images/clubbadges/web/s86.png)

`http://cdn.content.easports.com/fifa/fltOnlineAssets/2012/fut/items/web/6000263.json`

{
  "Badge": {
    "ClubId": "86",
    "LeagueId": "50",
    "NationId": "42",
    "Rating": "73",
    "Category": "1",
    "ItemType": "Badge",
    "Rare": "1"
  }
}

# Fun discoveries

* BLAH is the tallest player in the game. He's an OK goalkeeper, albeit a bit slow clumsy. I use him as a benchwarmer and only bring him on for last-minute corner kicks. Dude's taller than Crouch and connect headers with the force of  thousand suns.

* Is the smallest player in the game. Do it for the lulz.

# Please note

* Special edition cards are not tracked here
* You should not use/abuse the web services/API/URLs listed above - doing so will probably get you blacklisted on the FIFA servers and you'll find it hard to play online.
* Mapping for ClubId -> Club, LeagueId -> League, NationId -> Nation are beyond the scope of this project.