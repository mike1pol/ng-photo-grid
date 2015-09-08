# ng-photo-grid
Photo grid like facebook in angular js with no dependencies. Work well when images has different dimension, scale image but remain ratio. Also improve display image in cell too.

# [Examples page](http://jerryc-nguyen.github.io/ng-photo-grid/)

![angular facebook photo grid with default config](http://jerryc-nguyen.github.io/ng-photo-grid/demo-images/default.png)

![angular facebook photo grid with 2 bigs image first](http://jerryc-nguyen.github.io/ng-photo-grid/demo-images/2bigs.png)

![angular facebook photo grid with square config](http://jerryc-nguyen.github.io/ng-photo-grid/demo-images/square.png)


This module can be used with these options:

| Option         | Description                                                                                                                                 | Value    | Default        |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------|----------|----------------|
| urlKey         | object attribute present for image url  ex:{url:  "/example.jpg"} => urlKey: "url"                                                          | string   | "original_url" |
| sortByKey      | object attribute present for order of object in array ex:[{nth: 1}, {nth: 2}] => sortByKey: "nth"                                           | string   | "nth"          |
| onClicked      | image click event handler, argument of handler was clicked image object                                                                                      | function | none           |
| onBuilded      | callback event handler when grid was built completed                                                                                                      | function | none           |
| margin         | space between each image on grid                                                                                                            | number   | 2              |
| maxLength      | maximum objects in array grid choose to build                                                                                               | number   | 5              |
| isSquare       | options to build grid has the height equals to width ex: used to display grid of grids without break layout                                 | boolean  | false          |
| buildOnLoading | option to trigger build grid, building grid while images loading if it's true. Otherwise, grid will be built only one when all images loaded | boolean  | true           |

####Note: 

      This directive used to built the grid of images (let's look at the demo source code to see how the array of images loadedok like), so you should prepare the array of images object first in controller then following this guide below.

####1. Inject module to your angular app definition:
    
    angular.module("ngApp", ["ngPhotoGrid"])
    
####2. On your controller, you should define the options and events handler if needed like this:
   
      $scope.gridOptions = {
        urlKey      :     "original_url",
        sortKey     :     "nth",
        onClicked   :     function(image) {
                            alert(JSON.stringify(image))
                          },
        onBuilded   :     function() {
                            console.log ("built completed!")
                            $scope.isBuildingGrid = false;
                          },
        margin      :     2,
        maxLength   :     7
      }
   
####3. Use directive in template like this:
  
    <div ng-photo-grid="" images="images" grid-options="gridOptions"></div>
  
####4. Open browser then see the magic, you can refresh (F5) browser again to see others style of grid was built (if your images were random order and have different dimension)

####Others
  Contribution are welcome so if you find any issue, please post issues or email me at: jerryc.nguyen92[at]gmail.com
  
  
  Thanks [lorempixel.com](http://lorempixel.com) for better images in demo pages.
  
##MIT License

