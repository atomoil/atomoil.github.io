---
title:      Typescript for Browser Development
date:       2020-06-19 13:50:00
summary:    Setting up typescript and webpack for browser development
categories: [development, web, node, browser]

---

Follow these steps to setup a typescript browser project:

* [Webpack Getting Started](https://webpack.js.org/guides/getting-started/)
* [Webpack Typescript Setup](https://webpack.js.org/guides/typescript/)
* [Webpack watch](https://webpack.js.org/configuration/watch/)


Aka:


`npm install --save-dev webpack webpack-cli typescript ts-loader`

package.json (snip):

```
  "scripts": {
    "build": "webpack",
    "dev": "webpack --watch",
  }
```

tsconfig.json:

```
{
    "compilerOptions": {
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

webpack.config.js:

```
const path = require('path');

module.exports = {
  entry: './src/index.ts',
  output: {
    filename: '[name].bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
  devtool: 'inline-source-map',
  module: {
      rules: [
          {
              test: /\.tsx?$/,
              use: 'ts-loader',
              exclude: /node_modules/,
          },
      ],
  },
  resolve: {
      extensions: [ '.tsx', '.ts', '.js' ],
  },
  watchOptions: {
      ignored: /node_modules/,
  }
};
```

## Using Jest with typescript

[use `ts-jest`](https://github.com/kulshekhar/ts-jest)

aka

* `npm i -D jest ts-jest @types/jest`
* `npx ts-jest config:init` (to create jest config)

