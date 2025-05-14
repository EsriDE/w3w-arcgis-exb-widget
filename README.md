### Experience Builder Extensions Repo
# what3words Widget
### by [Niklas Köhn](https://github.com/esride-nik/), Esri Deutschland

---

## How to use this widget
Clone the sample repo into your Experience Builder Client root folder and restart your watcher.

## About
This is a widget developed for demonstration purposes at Esri Deutschland, using the what3words REST API. It's not been actively maintained since what3words cancelled their free API tier.

## Having issues?

### TS compiler cannot resolve import from '@what3words/api'
Try adding the path to the package explicitely to the typeRoots in tsconfig.json:
```
    "typeRoots": [
      "w3w-arcgis-exb-widget/node_modules/@what3words\\api/dist/lib/client"
    ],
```

### BREAKING CHANGE: webpack < 5 used to include polyfills for node.js core modules by default
It is what it is. Webpack 5, which comes with Experience Builder 1.8, doesn't include those polyfills anymore. Please refer to [this article for further reading](https://community.esri.com/t5/arcgis-experience-builder-questions/npm-packages-in-experience-builder-1-8/m-p/1181885).
Enhance your webpack files accordingly. The article says how to do that and you can find mine in the subfolder ``_webpack5-config-updates`` in this repo. Or use a [package like this one](https://www.npmjs.com/package/node-polyfill-webpack-plugin) to add them all back in.

## Ideas for further development
* search by text input, i.e. the geocoding of a three-word address (maybe use the w3w Locator Services instead of the REST API + JSAPI Search widget to take advantage of the built-in suggest functionality)
* convert selected vertices or point features to three-word addresses
* check which features are in the clicked 3x3 meter square
* connect with Directions Widget
* add switch in backend to show language dropdown on widget frontend
* parse url parameters to directly zoom to a w3w address
* implement widget output data source: https://developers.arcgis.com/experience-builder/guide/core-concepts/data-source/#widget-output-data-source 

## Participation
If you want to participate, please create a fork and send a pull request after developing a new feature. Feel free to open an issue to start a discussion or contact us directly! We are looking forward to your ideas and maybe even productive uses of the widget!  
