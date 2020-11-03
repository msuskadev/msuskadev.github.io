## Hello ~~world~~ bot

```javascript
import * as resify from 'restify';
import { BotFrameworkAdapter } from 'botbuilder';

const echoBotPort = 3900; 
const server = resify.createServer();

const adapter = new BotFrameworkAdapter({
    appId: process.env.MicrosoftAppId,
    appPassword: process.env.MicrosoftAppPassword
});

server.post('/api/messages', (req, res) => {
    adapter.processActivity(req, res, async (context) => { 
        await context.sendActivity(`You said: ${context.activity.text}`);
    });
});

server.listen(process.env.EchoBotPort, () => {
    console.log(`Server is listening on port ${echoBotPort}`);
});
```

Note:
Bot Adapter - The bot adapter encapsulates authentication processes and sends activities to and receives activities from the Bot Connector Service. When your bot receives an activity, the adapter creates a turn context object, passes it to your bot application logic, and sends responses back to the user's channel.