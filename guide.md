# Guide

* This note is build by [docsifyjs](https://github.com/docsifyjs)
* Theme is [Simple Dark](https://jhildenbiddle.github.io/docsify-themeable/#/themes)
    * [Theme]
## Build

* Install npm package

```bash
npm i docsify-cli -g
```

* It will generate a docs folder, and initialize it
    * Content
        * `index.html` as the entry file
        * `README.md` as the home page
        * `.nojekyll` prevents GitHub Pages from ignoring files that begin with an underscore

```
docsify init ./docs
```

* Local Test

```
docsify serve docs
```


* You can read the below reference to expand the features, e.g. sidebar, code highlighting...

> Reference：https://docsify.js.org/#/quickstart

## Deploy

* Create the repo, and upload the `docs` folder to repo root.
![](https://i.imgur.com/pWHOIca.png)
* You can specific your note's Domain name in the Github
![](https://i.imgur.com/m5oi19A.png)