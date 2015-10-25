TextformatterPageImages
=======================

## Syntax
* includes an image-tag in the Textfield by using [[fieldname(optional),number(optional),class(optional)]] 
* if using this module Names of Imagefields shouldn't start with a number
* If a class (CSS) is added Fieldname and/or Number and/or leading Comma is mandatory
* Comma is mandatory from two Parameters and up

Look at the Examples for easy understanding

## Examples
`[[]]` matches the first or only one picture in the first or only one image-field if exists  
`[[images]]` matches the first or only one picture in the named image-field  
`[[4]]` matches the fourth picture in the first or only one image-field  
`[[3,left]]` matches the third picture in the first or only one image-field and adds the class left  
`[[,right]]` matches the first or only one picture in the first or only one image-field and adds the class left  
`[[images,3,top]]` matches the third picture in the image-field named 'images' and adds the class top  

## Settings
* One or more basic classes could be added to the image tag
* Define markup for wrapper

## Hooks
function wrapper() is hookable with instance of <span style="color:blue;">Pageimage</span> as argument. The function return an array of 2 elements.   
`array([0]=>'markup_before_image_tag',[1]=>'markup_after_image_tag')`

## Compatibility
works proper together with other textformatters like markdown.

## Thanks
thanks to Diogo for the nice module TextformatterImageTags which is the mother of this module. 
