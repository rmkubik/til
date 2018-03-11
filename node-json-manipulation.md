# Json File Manipulation with Node
## tags
#json #node #require #stringify #javascript

## explanation
In my office we have some large JSON files that occasionally need duplicated updates in mutliple places. Node.js makes workgin with these files incredibly easy with two features. 

The first is that JSON files can be required as you import a module (`require('file.json')`) and then manipulated as it were any other JavaScript object. 

The second feature is not specific to Node, but is included in the `JSON.stringify()` function. The third parameter of `.stringify()` allows you to specify the number of spaces used when coverting a JavaScript object into a JSON string.

## examples
```javascript
const jsonFile = require('file.json');

jsonFile.newAttribute = false;
delete jsonFile.oldAttribute;

JSON.stringify(jsonFile, null, 2);
```

## sources
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify
