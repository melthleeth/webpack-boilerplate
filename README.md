# webpack-boilerplate

Boilerplate code for JavaScript project (update: 21.09.24)

## How to Start

- download or clone this project
- run `npm install`

## Contains

### webpack.config.js

```javascript
const path = require("path");

module.exports = {
  entry: "./src/index.js",
  output: {
    path: path.resolve(__dirname, "dist/assets"),
    filename: "bundle.js",
  },
  devServer: {
    static: {
      directory: path.join(__dirname, "dist"),
    },
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
          options: {
            presets: ["@babel/preset-env"],
          },
        },
      },
    ],
  },
};
```

### package.json

```javascript
 "scripts": {
    "build": "webpack --mode production",
    "serve": "webpack-dev-server --mode development"
  },
```
