### Simple React Native Demo

## About

This app was made using this tutorial: https://www.raywenderlich.com/126063/react-native-tutorial

This was a great introduction to React-Native and it was very easy for me to understand as it is almost identical to React. There were a few differences in syntax (component constructor methods) but its basically the same. When I finished the tutorial I realized that all of the property links were linking to the same property-show/view-listing page. Every link led to the same property, the first one in the list. I solved this problem by inspecting the JSON data which came back in the request. I realized that the tutorial uses a specific property, JSON_DATA.guid, to pass information to the view-listing component. The problem was that, for whatever reason, the JSON data I was getting back did not list the .guid property in any of its entries. This was resulting in the filter method filtering by undefined and therefore returning always the first property in the listings array. I solved this problem by simply changing the onPressed and rowPressed functions to identify properties by their title rather than by their non-existent .guid. 
