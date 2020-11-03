## How to connect FlyBot to QnAMaker.ai API?
```javascript
import { ActivityHandler, MessageFactory, TurnContext } from 'botbuilder';
import { LuisApplication, LuisRecognizer, QnAMaker } from 'botbuilder-ai';

export class FlyBot extends ActivityHandler {
    private luisRecognizer: LuisRecognizer;
    private qnaMaker: QnAMaker;

    constructor() {
        super();    
        
        const luisApplication: LuisApplication = {
            applicationId: 'Generated LUIS AI App ID',
            endpoint: 'Generated LUIS AI Endpoint',
            endpointKey: 'Generated LUIS AI Password'
        };

        this.qnaMaker = new QnAMaker({
            knowledgeBaseId: 'Generated QnA Marker Knowledge Base ID',
            endpointKey: 'Generated QnA Marker Endpoint Key',
            host: 'Generated QnA Marker Host'
        });


        const recognizerOptions = {
            apiVersion: 'v3'
        };

        this.luisRecognizer = new LuisRecognizer(luisApplication, recognizerOptions);        

        this.onMessage(async (context: TurnContext, next) => {                        
            const luisResult = await this.luisRecognizer.recognize(context);

            if (luisResult.intents.SearchFlight) {
                await context.sendActivity(MessageFactory.text(JSON.stringify(luisResult)));
            } else if (luisResult.intents.FAQ) {
                const qnaResults = await this.qnaMaker.getAnswers(context);
                await context.sendActivities(MessageFactory.text(JSON.stringify(qnaResults, null, 2)));
            }
                    
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

