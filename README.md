![spritesheet.js](http://i.imgur.com/RcHZ2qZ.png)
==============

Spritesheet.js is command-line spritesheet (a.k.a. Texture Atlas) generator written in node.js.

###Supported spritesheet formats###
* Starling / Sparrow
* JSON (i.e. PIXI.js)
* Easel.js
* cocos2d

###Usage###
1. **Command Line**
    ```bash
    $ spritesheet-js assets/*.png
    ```
    Options:
    ```bash
    $ spritesheet-js
    Usage: spritesheet-js [options] <files>

	Options:
      -f, --format  format of spritesheet (starling, sparrow, json, pixi.js, easel.js, cocos2d)                                                      [default: "json"]
      -n, --name    name of generated spritesheet                                                                                                    [default: "spritesheet"]
      -p, --path    path to export directory                                                                                                         [default: "."]
      --trim        removes transparent whitespaces around images                                                                                    [default: false]
      --square      texture should be s square                                                                                                       [default: false]
      --powerOfTwo  texture width and height should be power of two                                                                                  [default: false]
      --algorithm   packing algorithm: growing-binpacking (default), binpacking (requires passing width and height options), vertical or horizontal  [default: "growing-binpacking"]

    ```
2. **Node.js**
    ```javascript
    var spritesheet = require('spritesheet-js');
    
    spritesheet('assets/*.png', {format: 'json'}, function (err) {
      if (err) throw err;

      console.log('spritesheet successfully generated');
    });
  ```
  
###Trimming / Cropping###
Spritesheet.js can remove transparent whitespace around images. Thanks to that you can pack more assets into one spritesheet and it makes rendering a little bit faster.

*NOTE: Some libraries such as Easel.js or PIXI.js dont't support this feature.*
![Trimming / Cropping](http://i.imgur.com/76OokJU.png)

###Installation###
1. Install [ImageMagick](http://www.imagemagick.org/)
2. ```npm install spritesheet-js -g```

###Test###
```
mocha test
```

--------------
Thanks [Przemysław Piekarski](http://www.behance.net/piekarski) for logo design and assets in examples.
