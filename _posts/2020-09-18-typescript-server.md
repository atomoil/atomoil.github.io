---
title:      Typescript for Server Development
date:       2020-09-18 13:50:00
summary:    Setting up typescript and webpack for browser development
categories: [development, web, node, browser]

---


`npm i typescript ts-node-dev`

folder structure:

```
|- dist/
	|- index.js
|- package.json
|- src/
	|- index.ts
|- tsconfig.json	

```

package.json (snip):

```
  "scripts": {
    "build": "tsc",
    "start": "tsc && node ./dist/index.js",
    "dev": "ts-node-dev --respawn --transpileOnly ./src/index.ts"
  }
```

tsconfig.json:

```
{
    "compilerOptions": {
        "rootDir": "./src/",
        "outDir": "./dist/",
        "sourceMap": true,
        "noImplicitAny": true,
        "module": "es6",
        "target": "es5",
        "jsx": "react",
        "allowJs": true
    }
}
```
