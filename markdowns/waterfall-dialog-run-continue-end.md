## How to run, continue and end Dialog

```javascript
// begin or continue dialog 
public async run(context: TurnContext, accessor: StatePropertyAccessor<DialogState>) {
    const dialogSet = new DialogSet(accessor);
    dialogSet.add(this);

    const dialogContext = await dialogSet.createContext(context);
    const results = await dialogContext.continueDialog();
    if (results.status === DialogTurnStatus.empty) {        
        await dialogContext.beginDialog(this.id);
    }
}

// end dialog
private async finalStep(step: WaterfallStepContext) : Promise<DialogTurnResult>{
    if (step.result) {
       // call some API and send activities to channels
    }
    return await step.endDialog();
}
```