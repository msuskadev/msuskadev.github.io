## How to create Waterfall Dialog

```javascript
export class SearchFlightsDialog extends ComponentDialog {    
    constructor() {
        super(SEARCH_FLIGHTS_DIALOG);

        this.addDialog(new TextPrompt(FLY_FROM_TEXT, this.airportCountryCodeValidator.bind(this)))
            .addDialog(new TextPrompt(FLY_TO_TEXT, this.airportCountryCodeValidator.bind(this)))        
            .addDialog(new ChoicePrompt(TRAVEL_DATE_CHOICE))
            .addDialog(new DateTimePrompt(TRAVEL_DATE, this.dateTimePromptValidator.bind(this)))
            .addDialog(new ChoicePrompt(TRAVEL_ALONE_OR_WITH_FF_CHOICE))
            .addDialog(new NumberPrompt(NUMBER_OF_ADULTS))
            .addDialog(new NumberPrompt(NUMBER_OF_CHILDREN))
            .addDialog(new ConfirmPrompt(CONFIRM_PROMPT))
            .addDialog(new WaterfallDialog(WATERFALL_SEARCH_FLIGHTS_DIALOG, [
                this.getDepartureAirport.bind(this),
                this.getArrivalAirport.bind(this),
                this.choiceTravelDate.bind(this),
                this.getTravelDate.bind(this),
                this.isTravellingAlone.bind(this),
                this.getAdultsNumber.bind(this),
                this.getChildrenNumber.bind(this),
                this.summaryStep.bind(this),
                this.finalStep.bind(this),
            ]));
        
        this.initialDialogId = WATERFALL_SEARCH_FLIGHTS_DIALOG;
    }
    ...
}
```