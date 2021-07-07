
## CardFactory - creating sample card

```javascript
const { CardFactory } = require('botbuilder');

CardFactory.audioCard(
    'Fuel - Song',
    ['https://upload.wikimedia.org/wikipedia/en/7/78/Metallica_-_Fuel.ogg'],
    CardFactory.actions([
        {
            title: 'Read more',
            type: 'openUrl',
            value: 'https://en.wikipedia.org/wiki/Fuel_(song)'
        },
        {
            title: 'Open Spotify',
            type: 'openApp',
            value: 'spotify'
        }
    ]),
    {                
        subtitle: 'Album: Reload',
        text: `**"Fuel"** is a song by American heavy metal band **Metallica**.`
    }
);
```

Note:
* types: DownloadFile, 
ImBack	
MessageBack	
OpenApp	
OpenUrl	
Payment	
PlayAudio	
PlayVideo	
PostBack	
ShowImage	
Signin