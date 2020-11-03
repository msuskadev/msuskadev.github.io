## FlyBot

```javascript
import { ActivityHandler, MessageFactory } from 'botbuilder';

export class FlyBot extends ActivityHandler {
    constructor() {
        super();
        
        this.onMessage(async (context, next) => {
            const replyText = `You said: ${ context.activity.text }`;
            await context.sendActivity(MessageFactory.text(replyText));            
            await next();
        });

        this.onMembersAdded(async (context, next) => {
            const membersAdded = context.activity.membersAdded;
            if (!membersAdded) {
                return;
            }
            const welcomeText = 'Hello and welcome to JS Poland 2020!';
            for (const member of membersAdded) {
                if (member.id !== context.activity.recipient.id) {
                    await context.sendActivity(MessageFactory.text(welcomeText, welcomeText));
                }
            }
            await next();
        });
    }
}
```

Note:
IMPORTANT:
// Call the next continuation function from each handler to allow processing to continue. 
// If next is not called, processing of the activity ends.