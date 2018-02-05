# Use NPM's .bin directory instead of globally installing dependencies
## tags
#javascript #npm #global #dependency

## explanation
Until recently, I thought that npm modules with a command line interface needed to be installed globally before they could be used. I found an article (in the sources) that talks about creating an `npm run cli-app` command instead of globally installing. This works because npm keeps a `.bin` directory in `node_modules` that it references cli based apps you have installed like `gulp` or `grunt`. This `.bin` directory is added to the path of all `npm run` commands so you can just directly create a npm run script like this:

```javascript
. . .
"scripts": {
  "gulp": "gulp buildProject"
},
. . .
```

And then just call it from cli as `npm run gulp`. Now you have a versioned instance of gulp installed as a dev dependency just for this project instead of a global instance used across a variety of different projects.

## sources
https://codeburst.io/maybe-dont-globally-install-that-node-js-package-f1ea20f94a00
