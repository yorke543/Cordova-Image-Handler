#Cordova Image Handler Plugin
A plugin  developed by [@yorke543](https://github.com/yorke543) and [@bitgapp](https://github.com/bitgapp) for the manipulation of images in Android and iOS.

##How to use

This plugin provides a number of methods that can be used to manipulate images with the cordova framework. Installation is a simple process of running:

`cordova plugin add https://github.com/yorke543/Cordova-Image-Handler.git`

After the plugin has been installed succesfully, it is a simple case of calling the methods described below:

###base64ToJpg

```javascript

var options = {
   base64string:"data:image/png;base64,iVBORw0KGg.....", //full string excluded
	destDirectory:cordova.file.externalRootDirectory, //cordova file plugin can be used
	destFilename:"new-image"// exclude the file extension
}

var cb = function(error, value){
   if(error){
      //handle error - This is a friendly string explaining what went wrong
      return;
    }

   //returns filepath in the format 'file:///...' if successful
   var filePath = value;

}

window.ImageHandler.base64ToJpg(options, cb);
```

###resize

```javascript
var maxSize = 640,
    cb = function(error, value){
       if(error){
          //handle error
          return;
        }

       //returns filepath
       var filePath = value;
    };

window.ImageHandler.resize(fileLocation, maxsize, cb);
```


###thumbnail

```javascript
var cb = function(error, value){
   if(error){
      //handle error
      return;
    }

   //returns filepath
   var filePath = value;

}

window.ImageHandler.thumbnail(fileLocation, destDirectory, destFilename, size, cb);
```

###rotate

```javascript
var cb = function(error, value){
   if(error){
      //handle error
      return;
    }

   //returns filepath
   var filePath = value;

}

window.ImageHandler.rotate(fileLocation, cb);
```
