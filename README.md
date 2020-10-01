# Blood on the Clocktower Grimoire & Town Square

![image](https://user-images.githubusercontent.com/325521/80531231-8f473980-899a-11ea-96d6-edbf79337cb5.png)

This is an unofficial online tool to run Blood on the Clocktower games through Discord or other digital means.
It is supposed to aid storytellers and allow them to quickly set up and capture game states for their players.

[You can try it online!](https://bra1n.github.io/townsquare)

### Features

- Public Town Square and Storyteller Grimoire (toggle with **shortcut \[G\]**)
- Supports custom script JSON generated by the [Script Tool](https://bloodontheclocktower.com/script)
- Live Session for Storyteller / Players including live voting!
- Includes all 3 base editions and travelers
- Night sheet and reminder text for each character ability to help storytellers
- Many other customization options!

### Custom Characters

In order to add custom characters to your local Grimoire, you need to create a JSON definition for them,
similar to what is provided in the [`roles.json`](https://github.com/bra1n/townsquare/blob/main/src/roles.json) for the 3 base editions. Here's an example of how such a character
definition file might be written:

```json
[
  {
    "id": "acrobat",
    "image": "https://github.com/bra1n/townsquare/blob/main/src/assets/icons/acrobat.png?raw=true",
    "edition": "custom",
    "firstNight": 0,
    "firstNightReminder": "",
    "otherNight": 49,
    "otherNightReminder": "If either good living neighbor is drunk or poisoned, the Acrobat dies.",
    "reminders": ["Die"],
    "remindersGlobal": [],
    "setup": false,
    "name": "Acrobat",
    "team": "outsider",
    "ability": "Each night*, if either good living neighbor is drunk or poisoned, you die."
  },
  { 
    "id": "investigator" 
  },
  { 
    "id": "imp" 
  }
]
```

This definition JSON includes a custom character, the Acrobat, and 2 base game characters, the Investigator and the Imp.
For base game characters, it is sufficient to only provide the ID, similar to what you get from the Script Tool.

**Required properties:** `id`, `name`, `team`, `ability`

- **id**: the internal ID for this character, without spaces or special characters
- **image**: a URL to a PNG of the character token icon (should have a transparent background!)
- **edition**: the ID of the edition for this character. can be left blank or "custom"
- **firstNight** / **otherNight**: the position that this character acts on the first / other nights, compared to all
  other characters
- **firstNightReminder** / **otherNightReminder**: reminder text for first / other nights
- **reminders**: reminder tokens, should be an empty array `[]` if none
- **remindersGlobal**: global reminder tokens that will always be available, no matter if the character is assigned to a player or not
- **setup**: whether this token affects setup (orange leaf), like the Drunk or Baron
- **name**: the displayed name of this character
- **team**: the team of the character, has to be one of `townsfolk`, `outsider`, `minion`, `demon` or `traveler`
- **ability**: the displayed ability text of the character

_Note:_ custom characters are currently not supported in live sessions and will not be synchronised to other players.

## [Code of Conduct](CODE_OF_CONDUCT.md)

## [Contributing](CONTRIBUTING.md)

## Acknowledgements and Copyrights

* [Blood on the Clocktower](https://bloodontheclocktower.com/) is a trademark of Steven Medway and [The Pandemonium Institute](https://www.thepandemoniuminstitute.com/)
* Night reminders and other auxiliary text written by [Ben Finney](http://bignose.whitetree.org/projects/botc/diy/)
* Iconography by [Font Awesome](https://fontawesome.com/)
* Background image by [Ryan Maloney](https://www.artstation.com/maloney94)
* Webfonts by [Google Fonts](https://fonts.google.com/) and [Online Web Fonts](https://www.onlinewebfonts.com/)
* All other images and icons are copyright to their respective owners

This project and its website are provided free of charge and not affiliated with The Pandemonium Institute in any way.

## Donations
This project will always be available free of charge, since I love building cool things and playing Blood on the Clocktower. If you still want to support me with a donation, you can do that here:

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/bra1n)
