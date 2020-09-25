## How to create Waterfall Dialog

```javascript
private async getDepartureAirport(step: WaterfallStepContext) : Promise<DialogTurnResult> {
        return await step.prompt(FLY_FROM_TEXT, `Please enter departure airport (like WRO, JFK) or 
            country code (PL, DE)`);
}

private async getArrivalAirport(step: WaterfallStepContext) : Promise<DialogTurnResult> {
    const flight = step.options as FlightModel;
    flight.flyFrom = step.result.toUpperCase();

    return await step.prompt(FLY_TO_TEXT, `Where would you like to arrive at?
        (IATA Airport Code or Country Code)`);
}

private async choiceTravelDate(step: WaterfallStepContext) : Promise<DialogTurnResult>{
    const flight = step.options as FlightModel;
    flight.flyTo = step.result.toUpperCase();

    return await step.prompt(TRAVEL_DATE_CHOICE, {
        choices: ChoiceFactory.toChoices(['Today', 'Tomorrow', 'Other Date']),
        prompt: 'When do you want to travel?'
    });
}
```