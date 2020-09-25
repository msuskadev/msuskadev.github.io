
## Advanced Echo Bot - Server

```javascript
import * as resify from 'restify';
import { BotFrameworkAdapter } from 'botbuilder';
import { EchoBot } from './bot/echo-bot';

const server = resify.createServer();
const adapter = new BotFrameworkAdapter({
    appId: process.env.MicrosoftAppId,
    appPassword: process.env.MicrosoftAppPassword
});

const echoBot = new EchoBot();
server.post('/api/messages', (req, res) => {
    adapter.processActivity(req, res, async (context) => { 
        await echoBot.run(context);
    });
});

server.listen(process.env.EchoBotPort, () => {
    console.log(`Server is listening on port ${echoBotPort}`);
});
```