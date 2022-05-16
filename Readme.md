# Creating Angular Elements

To generate angular elements/web components use the following steps.

After creating and done work with your angular project use the following steps to generate it as angular element.

## Step 1

## Install angular elements

Install angular elements by using the command

```
npm install @angular/elements
```

## Step 2

## Create a selector tag

Create a selector tag using 'createCustomElement' by adding the following code in app.module.ts

![This is an image](https://raw.githubusercontent.com/thrinathreddynarahari/ngElements/main/appmodulets.png)

## Step 3

## Generate Build for the project

Generate Build for the project using the following command

```
ng build  --output-hashing None
```

this will generate a dist folder in your project directory.

## Step 4

## Create js file

Create a js file in your project level by name 'build-component.js'

Include the following code in your js file

```
const fs = require("fs-extra");
const concat = require("concat");

build = async () => {
  const files = [
    "./dist/angular-poc/runtime.js",   //change path of your runtime.js
    "./dist/angular-poc/polyfills.js", //change path of your polyfills.js
    "./dist/angular-poc/main.js",      //change path of your main.js
  ];

  await fs.ensureDir("login");                     //change dirctory name
  await concat(files, "login/login-widget1.js");   //change path
};
build();

```

After adding the code should look like this:

![This is an image](https://raw.githubusercontent.com/thrinathreddynarahari/ngElements/main/buildcomponent.png)

## Step 5

## Include build in package.json

Include the following code in scripts in package.json

```
"build:elements": "ng build --prod --output-hashing none && node build-component.js"
```

Package.json should look like this

![This is an image](https://raw.githubusercontent.com/thrinathreddynarahari/ngElements/main/packagejson.png)

## Step 6

## Install the fs-extra

Install fs-extra package by following command

```
npm install fs-extra concat
```

## Step 7

## Concatinating all js files

Concatinating all js files into a single js file using the following command

```
npm run build:elements
```

This will generate a folder consiting of the js file which is ready to use.
