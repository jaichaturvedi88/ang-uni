# AngUni

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 8.0.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## 01-universal-integration - **This branch is working now**
> ng add @nguniversal/express-engine --clientProject ang-uni
- after running this command there is an error in app.module.ts, 
- **.withServerTransition({ appId: 'serverApp' })** is added twice 
> npm run build:ssr && npm run serve:ssr
- To start rendering your app with Universal on your local system

## 02-firebase-integration - **Intergrated but not deployed**
> npm install firebase @angular/fire
- This will install firebase in pfroject

After above step 
> **npm run build:ssr** --> will the project

> **npm run serve:ssr** --> this will give some wierd issue

<br>

To fix the above issue change **--bundleDependencies all** to **--bundleDependencies none** in package.json as show below

```
"build:client-and-server-bundles": "ng build --prod && ng run ang-uni:server:production --bundleDependencies all"
```  
```
"build:client-and-server-bundles": "ng build --prod && ng run ang-uni:server:production --bundleDependencies none"
```

Now if we try to run the app, it should work in local using below command 
**npm run serve:ssr** 


