jQueryMask-Bootstrap
====================

This is a masked input plugin for the jQuery javascript library. It allows a user to more easily enter fixed width input where you would like them to enter the data in a certain format (dates,phone numbers, etc). It has been tested on Internet Explorer, Firefox, Safari, Opera, and Chrome. A mask is defined by a format made up of mask literals and mask definitions. Any character not in the definitions list below is considered a mask literal. Mask literals will be automatically entered for the user as they type and will not be able to be removed by the user.The following mask definitions are predefined:

• a - Represents an alpha character (A-Z,a-z)<br>
• 9 - Represents a numeric character (0-9) <br>
• * - Represents an alphanumeric character (A-Z,a-z,0-9)<br>

Instalation
====================

First, include the jQuery and masked input javascript files.
```
<script src="jquery.js" type="text/javascript"></script>
<script src="jquery.maskedinput.js" type="text/javascript"></script>
```
<br>
Next, call the mask function for those items you wish to have masked.
```
jQuery(function($){
   $("#date").mask("99/99/9999");
   $("#phone").mask("(999) 999-9999");
   $("#tin").mask("99-9999999");
   $("#ssn").mask("999-99-9999");
});
```
<br>
Optionally, if you are not satisfied with the underscore ('_') character as a placeholder, you may pass an optional argument to the maskedinput method.
```
jQuery(function($){
   $("#product").mask("99/99/9999",{placeholder:" "});
});
Optionally, if you would like to execute a function once the mask has been completed, you can specify that function as an optional argument to the maskedinput method.

jQuery(function($){
   $("#product").mask("99/99/9999",{completed:function(){alert("You typed the following: "+this.val());}});
});
```
<br>
You can now supply your own mask definitions.
```
jQuery(function($){
   $.mask.definitions['~']='[+-]';
   $("#eyescript").mask("~9.99 ~9.99 999");
});
```
<br>
You can have part of your mask be optional. Anything listed after '?' within the mask is considered optional user input. The common example for this is phone number + optional extension.
```
jQuery(function($){
   $("#phone").mask("(999) 999-9999? x99999");
});
```
<br>
If your requirements aren't met by the predefined placeholders, you can always add your own. For example, maybe you need a mask to only allow hexadecimal characters. You can add your own definition for a placeholder, say 'h', like so: $.mask.definitions['h'] = "[A-Fa-f0-9]"; Then you can use that to mask for something like css colors.

```
jQuery(function($){
   $("#phone").mask("#hhhhhh");
});
```
<br>
By design, this plugin will reject input which doesn't complete the mask. You can bypass this by using a '?' character at the position where you would like to consider input optional. For example, a mask of "(999) 999-9999? x99999" would require only the first 10 digits of a phone number with extension being optional.
<br><br><br>
&copy; Copyright 2013 - <a href="http://www.noweb.com.br" title="Noweb Publicidade">Noweb Publicidade</a> - Released under the MIT license.
<br>
This project is a version of <a href="http://digitalbush.com/projects/masked-input-plugin/" target="_blank">Masked Input Plugin</a>
