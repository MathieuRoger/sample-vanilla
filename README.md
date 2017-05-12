# HTML5 howtos

There exists several techniques to write a web app. 

Basically : templating or not templating.


## Vanilla-js : the non templating way

Here, we will explain a classical vanilla js single page application.

The key points of the technique:

* Only one index.html almost empty, that includes the main.js
* All html elements are created through js

### How to create an html element

See also:
* http://stackoverflow.com/questions/3297143/dynamically-create-a-html-form-with-javascript
* http://stackoverflow.com/questions/5536596/dynamically-creating-html-elements-using-javascript

Extract form above:
“
The HTML part:
<html>
 <head></head>
 <body>

 <body>
</html>

The javascript:
<script>
//create a form
var f = document.createElement("form");
f.setAttribute('method',"post");
f.setAttribute('action',"submit.php");

//create input element
var i = document.createElement("input");
i.type = "text";
i.name = "user_name";
i.id = "user_name1";

//create a checkbox
var c = document.createElement("input");
c.type = "checkbox";
c.id = "checkbox1";
c.name = "check1";

//create a button
var s = document.createElement("input");
s.type = "submit";
s.value = "Submit";

// add all elements to the form
f.appendChild(i);
f.appendChild(c);
f.appendChild(s);

// add the form inside the body
$("body").append(f);   //using jQuery or
document.getElementsByTagName('body')[0].appendChild(f); //pure javascript

</script>
This way you can create as many elements as you want dynamically.
“

### Performance issues

Each modification of the DOM (e.g., document.createElement) have its cost, and when doing huge modification, the string way is more performant:
 


# Miscellaneous information

* If you are planning to call REST web service : the server of the REST and the server sending the html page should be in the same server (constraint because of XSS)
* document.ready is called when all the js have been loaded so this is where we put the main


