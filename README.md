### Simple React Native Demo


In order to install this app and play around/modify it:
+ click "download zip" or do a pull request
+ run npm install in the root folder of the project
+ navigate to the /ios folder
+ open WeatherProject.xcodeproj/ in your text editor
+ open the directory in your text editor
+ In xcode, the play button in the top left runs the simulator
    - note: I was getting an error which was fixed by the method outlined here:
    http://stackoverflow.com/questions/25908604/error-objc-class-appdelegate-referenced-from-and-error-linker-command-f
+ In your text editor, play around with the components to your hearts content


This app was made using this tutorial: https://www.raywenderlich.com/126063/react-native-tutorial



This was a great introduction to React-Native and it was very easy for me to understand as it is almost identical to React. There were a few differences in syntax (component constructor methods) but its basically the same. When I finished the tutorial I realized that there was a bug. The problem was this: no matter which property you selected from the list in the "Search Results" page, you were always directed to the same property. They were routing to the right component, Property View, but this view Component was always only showing the first listing's data. I first looked at the JSON data which came back in the API request, but it was all good - the listings array had 20 unique property objects. I decided to trace the problem. When the API request comes back, the listings array is passed into the SearchResults component. In the SearchResults component, the app shows all of the listings in the array and waits for a button item to be pressed. In the old code, when a button element was pressed it was searching the array for something that matched something about itself. There was an error here where it was matching based on a quality (.guid) which it no longer had (maybe the API changed). My first fix was to have it match by it's title instead, something it definitely had. This was done by simply changing the onPressed and rowPressed functions to identify properties by their title ('.title') rather than by their non-existent '.guid'. In writing this, though, I realized that I should scrap the search-by-match thing all together and just have the button item pass itself immediately. Seems so obvious in retrospect.

TL;DR/Followed a tutorial. Learned that React-Native is almost identical to React.js. Fixed a bug.


####Search Page (Home):

<img src="https://raw.github.com/bradneal14/PropertyFinder/master/readme_assets/H.png" width="420">


####Search Results:

<img src="https://raw.github.com/bradneal14/PropertyFinder/master/readme_assets/SR.png" width="420">




####Property View:


<img src="https://raw.github.com/bradneal14/PropertyFinder/master/readme_assets/PV.png" width="420">
