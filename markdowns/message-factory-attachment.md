
## MessageFactory - attachment method

```javascript
const message = MessageFactory.attachment(
    CardFactory.heroCard(
        'Air Jordan XIII',
        ['http://example.com/air-jordan/xiii/flint-grey'],
        ['Buy']
     )
);

await context.sendActivity(message);
```