# Encode and Decode URIs
## tags
#javascript #encode #decode #component #uri #url

## explanation
JavaScript has a lot of built in functions to handle common issues developers run into like manipulating URLs. 

I just learned about two pairs of conveninent functions:
 - encodeURI(url)
 - decodeURI(url)
 - encodeURIComponent(url)
 - decodeURIComponent(url)

The `encode/decodeURIComponent` functions encode/decode every character except the following:

```A-Z a-z 0-9 - _ . ! ~ * ' ( )```

The non-component functions have additional characters that aren't encoded/decoded:

```;,/?:@&=+$#```

## examples
```javascript
encodeURIComponent('?x=шеллы'); // %3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B
encodeURIComponent('?x=test'); // %3Fx%3Dtest

const reservedCharacters = ";,/?:@&=+$#";
const unescapedCharacters = "-_.!~*'()";
const alphanumericAndSpaces = "ABC abc 123";

encodeURI(reservedCharacters); // ;,/?:@&=+$#
encodeURI(unescapedCharacters); // -_.!~*'()
encodeURI(alphanumericAndSpaces); // ABC%20abc%20123 (the space gets encoded as %20)

encodeURIComponent(reservedCharacters); // %3B%2C%2F%3F%3A%40%26%3D%2B%24%23
encodeURIComponent(unescapedCharacters); // -_.!~*'()
encodeURIComponent(alphanumericAndSpaces); // ABC%20abc%20123 (the space gets encoded as %20)
```

## sources
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent
