# Summary
Text-backdrop is a text-contextualization tool that takes a string and returns some relevant news, images, and wikipedia summaries. This module exports a single function which will take a string and return a promise that (when fulfilled) will return an object with contextual information (described below).

## How to use
```javascript
var backdrop = require('text-backdrop');
backdrop('Donald Trump is running for president in 2016').then(console.log)
```
## Results
```bash
{
    original_text: 'Donald Trump is running for president in 2016'
    named_entities: {'Donald Trump': {confidence: ...}}
    textTags: {'right_politics': .1244, 'energy': .0954, 'left_politics': .1674}
    keywords: {'2016': .2015, donald: .2385, trump: .2337}
    news: [{title: 'Presidential Horse Race 2016....', url: ...}, {title: 'Election 2016: Donald Trump...', url: ...}, ...]
    'Donald Trump': {
        images: ...
        summary: 'Donald John Trump (born on June 14, 1946) is an American...'
    }
}
```
## Explanation of Results
The results are a JSON object containing all extracted relevant information. We notice that the tool returns named entities (i.e. people, places, and organizations), categorical tags of the text, keywords from the text, relevant news (given the keywords), and images and a wikipedia summary for each named entity.

