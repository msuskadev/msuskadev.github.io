
## FlyBot - Server

```javascript
import * as resify from 'restify';
import { BotFrameworkAdapter } from 'botbuilder';
import { FlyBot } from './bot/fly-bot';

const flyBotPort = process.env.FlyBotPort || 3900; 

const server = resify.createServer();
const adapter = new BotFrameworkAdapter({
    appId: process.env.MicrosoftAppId,
    appPassword: process.env.MicrosoftAppPassword
});

const flyBot = new FlyBot();
server.post('/api/messages', (req, res) => {
    adapter.processActivity(req, res, async (context) => { 
        await flyBot.run(context);
    });
});

server.listen(process.env.FlyBotPort, () => {
    console.log(`Server is listening on port ${flyBotPort}`);
});
```