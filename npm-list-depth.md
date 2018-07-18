# Npm List Installed Packages
## tags
#javascript #node #npm

## explanation
Listing npm dependencies with `npm list` is a handy feature to checkout what npm packages you've installed. However, by default this lists not only the packages you've explicitly installed but the entire dependency tree too. I usually only find myself looking for the top level packages I've installed and this is where the `--depth` flag comes in handy.

## examples
command
```bash
npm list --depth=0
```

output
```bash
├── concat@1.0.3
├── gatsby-cli@1.1.58
└── npm@5.6.0
```

## sources
https://gist.github.com/yyx990803/6045243
