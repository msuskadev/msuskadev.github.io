## How to connect to LUIS.ai API?
```javascript
import { LuisApplication, LuisRecognizer } from 'botbuilder-ai';

const luisApplication: LuisApplication = {
    applicationId: 'Generated LUIS AI App ID',
    endpoint: 'Generated LUIS AI Endpoint',
    endpointKey: 'Generated LUIS AI Password'
};

const recognizerOptions = {
        apiVersion: 'v3'
};

this.luisRecognizer = new LuisRecognizer(luisApplication, recognizerOptions);        
const result = await this.luisRecognizer.recognize(turnContext);
```

