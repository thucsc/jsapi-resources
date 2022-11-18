# ArcGIS API for JavaScript with Angular CLI

This repo demonstrates how to use [@arcgis/core](https://www.npmjs.com/package/@arcgis/core) ES modules with Angular. 

---
## Known issues
* In order to use the APIs TypeScript [decorators](https://developers.arcgis.com/javascript/latest/api-reference/esri-core-accessorSupport-decorators.html), set the [`useDefineForClassFields`](https://www.typescriptlang.org/tsconfig#useDefineForClassFields) option to `false` in `tsconfig.compilerOptions`.

* There is an optimization bug affecting production builds at Angular `12.2.x`. It is recommended to upgrade to Angular 13+. For more information: https://github.com/Esri/feedback-js-api-next/issues/131.

* If you are seeing `404` errors in the console after updating Angular `12.1.x` dependencies, you should try clearing your browser cache. This is an Angular caching issue. 

* To prevent `Unhandled Promise Rejection` errors when using Angular with Zone.js, upgrade to Angular 13+, Zone.js `0.11.4` or greater, and switch the `tsconfig.target` to `es2017` or greater.

* If you are seeing CommonJS or AMD dependency warnings you can supress them in your build output through a property setting in `angular.json`, this won't affect functionality. This may not be needed if you upgrade to Angular 15+. Also, consider upgrading to the latest version of the ArcGIS JS API by running `npm i @arcgis/core@latest`.

*angular.json*

```json
  "allowedCommonJsDependencies": [
    "moment"
  ],
```
---

## Get Started

**Step 1** - Run `npm install` and then start adding modules.

**Step 2** Configure CSS.

*styles.css*

```css
  @import 'https://js.arcgis.com/4.25/@arcgis/core/assets/esri/themes/light/main.css';
```

For additional information, see the [Build with ES modules](https://developers.arcgis.com/javascript/latest/es-modules/) Guide topic in the SDK.

## Requirements

* If you are using Zone.js, the minimum version is `0.11.4 (February 10, 2021)` or greater.

## TypeScript

Currently, due to limitations in TypeScript, the APIs [autocasting](https://developers.arcgis.com/javascript/latest/programming-patterns/#autocasting) functionality works best in non-TypeScript applications. No changes are required if you are already using the API without any TypeScript build errors.

This sample implements strict class initalization, for more information visit the [TypeScript documentation](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-7.html#strict-class-initialization) page.

Check the online Angular documentation for their minimum TypeScript requirements for each release.

## Commands

For a list of all available `npm` commands see the scripts in `package.json`. 

### Development server

Run `ng serve --open` for a dev server that will automatically open a browser window. The app will automatically reload if you change any of the source files. You need to install [Angular CLI](https://cli.angular.io/) before you can compile the app. 

### Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. 

### Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
