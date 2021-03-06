OpenLayers Drawing Features Plugin
===================
[![Build Status](https://travis-ci.org/HamHamFonFon/ol3-drawFeatures.svg?branch=master)](https://travis-ci.org/HamHamFonFon/ol3-drawFeatures)

Welcome !! DrawFeatures is an OpenLayers 3 plugin for drawing new features, edit or delete feature from map. See [usage](https://rawgit.com/HamHamFonFon/ol3-drawFeatures/master/examples/index.html) for demo.
In progress: compatibility with NPM and Openlayers 4

Requirements
-------------
 - Openlayers 3


Getting started
-------------
  - Clone the repository : `git clone git@github.com:HamHamFonFon/ol3-drawFeatures.git ol3-drawFeatures`
  - Adding script JS and style CSS on your HTML code

Getting started with NPM
-------------
  - `npm install --save ol3-draw-features`


Demo examples
-------------

This exemples is showing how to use the plugin with Openlayers 3
	
  - [Basic usage](https://cdn.rawgit.com/HamHamFonFon/ol3-drawFeatures/82f29a3f/examples/basic_use.html) : you can add new features to the map, then editing or deleting them

  - [Use Locale Storage](https://cdn.rawgit.com/HamHamFonFon/ol3-drawFeatures/82f29a3f/examples/local_storage.html) : use localStorage to store features

Use with NPM : in progress...

API
-------------

### `new ol.control.ControlDrawButtons(vector_layer, opt_options)`

#### vector_layer
Layer you will adding, edit or delete features
```javascript
var vector_draw = new ol.layer.Vector({
    source: new ol.source.Vector(),
    style: new ol.style.Style({
        fill: new ol.style.Fill({
            color: 'rgba(255, 255, 255, 0.2)'
        }),
        stroke: new ol.style.Stroke({
            color: '#ffcc33',
            width: 2
        }),
        image: new ol.style.Circle({
            radius: 7,
            fill: new ol.style.Fill({
                color: '#ffcc33'
            })
        })
    })
});
```

#### Options parameters

|Option name|Type|Description|
 ----------------- | ---------------------------- | ------------------
| `style_buttons` |`String`| Use bootstrap glyphicon or default CSS. Values : `glyphicon|default`|
| `local_storage` |`Boolean`| (in progress) Possibility to record Layer in Local Storage
| `draw`          |`Array`| Select buttons to show|
|  - Point      |`Boolean`|Show point button|
|  - LineString    |`Boolean`|Show line button|
|  - Square        |`Boolean`|Show square button|
|  - Circle        |`Boolean`|Show circle button|
|  - Polygon       |`Boolean`|Show polygon button|


#### Exemple usage with Openlayers 3

```javascript
var optionsControlDraw = {
    "style_buttons" : (undefined !== typeof style_buttons)? "glyphicon" : "default",
    "local_storage": true,
    "draw": {
        "Point": true,
        "LineString": true,
        "Square": true,
        "Circle": true,
        "Polygon": true
    }
};
var buttonsDrawControls = new ol.control.ControlDrawFeatures(myVectorLayer, optionsControlDraw);
```

#### Exemple usage with NPM modules and Openlayers 4
In progress...

#### Extends

`ol.control.Control`

#### Methods

##### `setSelectedLayer()`
Set a layer who may be different tha the one in options array
```javascript
buttonsDrawControls.setSelectedLayer(otherVectorLayer);
```
  
Author(s)
-------------
Stéphane MÉAUDRE
 <stephane.meaudre@gmail.com> <smeaudre@kaliop.com>

Licence
-------------
MIT Licence - 2016

See also
-------------
My POC based on [Kuzzle](http://kuzzle.io/) : [Kurtography](https://github.com/HamHamFonFon/kurtogaphy)


README.md edited by [StackEdit](https://stackedit.io)
