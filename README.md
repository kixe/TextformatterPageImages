Textformatter Page Images
=========================

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
* Define custom markup for wrapper. Any PageImage property surrounded by curled brackets will be replaced by the related value. Additional properties (*class*, *index*, *urlSmall*, *urlMedium*, *urlLarge*) available. Default markup:  

```
<img class="{class}" src="{url}" alt="{description}"/>
```

## Hooks
function wrapper() is hookable with instance of <span style="color:blue;">Pageimage</span> as argument.

## Compatibility
Works well with other text formatters such as Markdown.

## Thanks
to Diogo for the nice module TextformatterImageTags which is the mother of this module. 
