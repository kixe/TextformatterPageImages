Textformatter Page Images
==========================

## Syntax
* Include images stored site-wide and over multiple ProcessWire instances in textfields by using the following tag syntax:
* **Classic**  `[[fieldname(optional),number(optional),class(optional),page-ID(optional),path-to-instance(optional)]]`
* **Markdown**  
  `![alt-Attribute(optional)](fieldname(optional),number(optional),class(optional),page-ID(optional),path-to-instance(optional))`
* If a class (CSS) is added fieldname and/or number and/or leading comma is mandatory.
* @ and spaces allowed in class names.
* Comma is mandatory from two parameters and up.
* Do not use spaces before or after commata (parameter separator).

## Usage Examples
+ `![]()` or `[[]]` matches the first or only one picture in the first or only one image-field if exists.
+ `![](images)` or `[[images]]` matches the first or only one picture in the named image-field.
+ `![](4)` or `[[4]]` matches the fourth picture in the first or only one image-field.
+ `![](3,left)` or `[[3,left]]` matches the third picture in the first or only one image-field and adds the class left.  
+ `![](,right)` or `[[,right]]` matches the first or only one picture in the first or only one image-field and adds the class left.
+ `![](images,3,top)` or `[[images,3,top]]` matches the third picture in the image-field named 'images' and adds the class top.  
+ `![](,,,1234)` or `[[,,,1234]]` matches the first or only one picture in the first or only one image-field of the page with ID = 1234.
+ `![](images,3,top,1234)` or `[[images,3,top,1234]]` matches the third picture in the image-field named 'images' of the page with ID = 1234 and adds the class top.
+ `![](images,3,top,1234,site-foo)` or `[[images,3,top,1234,site-foo]]` matches the third picture in the image-field named 'images' of the page with ID = 1234 of the ProcessWire instance living under the path '/site-foo/' adds the class 'top' and overwrites alt-Attribute with 'Hello World'.
+ `![Hello World](images,3,top,1234)`matches the third picture in the image-field named 'images' of the page with ID = 1234 adds the class 'top' and overwrites alt-Attribute with 'Hello World'.

## Module settings
### Markup

Define html wrapper in module settings. Default markup:  

	```
	<img class="{class}" src="{url}" alt="{alt}"/>
	```

Use placeholders surrounded by curled brackets to assign **PageImage** properties in the markup: 

+ *description*
+ *url*
+ *index*
+ *class*
+ *alt* (if set, or *description* as fallback is set)


### Size Variations
URLs of variations to be accessed via additional **PageImage** properties:

|VARIATION|small|medium|large|
|:-|:-|:-|:-|
|**width**|400|800|1200|
|**property (URL)**|*urlSmall*|*urlMedium*|*urlLarge*|


To use **PageImage** property surrounded by curled brackets will be replaced by the related value. Additional properties (*class*, *index*, *urlSmall*‌, *urlThumb* [alias of *urlSmall*], *urlMedium*, *urlLarge*) available.


## Hooks
Function `wrapper()` is hookable with instance of **PageImage** as argument.

## Compatibility
Works well with other text formatters such as Markdown. Place this textformatter before Markdown.  
Conflicts with markdown prevented by checking against the presence of ***negation indicator*** in the 1st parameter:
+ `https://`, `http://` or `/`
+ `.` (dot) which determines file extension (.png, .jpg)


## External Usage example
Useful to stay consistent with the markup stored in modules setup.

```
if ($page->image instanceof PageImage) {
    $class = "uk-width-1-2@l uk-width-1-2@m";
    $TPI = $modules->get('TextformatterPageImages');
    $TPI->assignImageProperties($page->image, ['class' => $class]);
    $page->_imageMarkupString = $TPI->renderMarkup($page->image);
}
```

## Limitations

* If using this module the names of imagefield to be used shouldn't start with a digit or underscore. (prevent mixup with image number)

## Thanks
to Diogo for the nice module **TextformatterImageTags** which is the mother of this module. 
