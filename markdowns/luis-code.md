## How to connect FlyBot to LUIS.ai API?
```javascript
import { ActivityHandler, MessageFactory, TurnContext } from 'botbuilder';
import { LuisApplication, LuisRecognizer } from 'botbuilder-ai';

export class FlyBot extends ActivityHandler {
    private luisRecognizer: LuisRecognizer;
    
    constructor() {
        super();    
        
        const luisApplication: LuisApplication = {
            applicationId: 'Generated LUIS AI App ID',
            endpoint: 'Generated LUIS AI Endpoint',
            endpointKey: 'Generated LUIS AI Password'
        };

        const recognizerOptions = {
            apiVersion: 'v3'
        };

        this.luisRecognizer = new LuisRecognizer(luisApplication, recognizerOptions);        

        this.onMessage(async (context: TurnContext, next) => {                        
            const luisResult = await this.luisRecognizer.recognize(context);
            await context.sendActivity(MessageFactory.text(JSON.stringify(luisResult)));            
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

