# Title
## tags
#tag

## explanation

## examples
```bash
# cat will print contents of package.json to the console
cat package.json
{
  "name": "repository",
  "scripts": {
    "build": "cross-env NODE_ENV=production webpack --progress --config webpack/prod.js",
    "start": "cross-env NODE_ENV=local webpack-serve --config webpack/dev.js",
  },
  "dependencies": {
    "lodash": "4.17.10"
  }
}


# If you pipe data into `jq` it will pretty print it with syntax highlighting
cat package.json | jq
{
  "name": "repository",
  "scripts": {
    "build": "cross-env NODE_ENV=production webpack --progress --config webpack/prod.js",
    "start": "cross-env NODE_ENV=local webpack-serve --config webpack/dev.js",
  },
  "dependencies": {
    "lodash": "4.17.10"
  }
}

# Finally jq lets you parse the JSON via dot notation
cat package.json | jq .scripts
{
  "build": "cross-env NODE_ENV=production webpack --progress --config webpack/prod.js",
  "start": "cross-env NODE_ENV=local webpack-serve --config webpack/dev.js",
}

cat package.json | jq .scripts.start
"cross-env NODE_ENV=local webpack-serve --config webpack/dev.js"
```

## sources
