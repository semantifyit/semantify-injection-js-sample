# Semantify.it Demo
Demo website for the [semantify.it service](https://semantify.it/). Shows how semantic annotations can be loaded at runtime and be crawled by engines like google's Data Testing Tool or [semantify.it's semantic validator](https://semantify.it/validator/). 

The *index.html* includes the code to dynamically append semantic data from a remote source, eg. semantify.it annotations through the url of the annotation. 

JS snippet to inject semantic data with basic Javascript:
```javascript
function appendAnnotation() {
    var element = document.createElement('script');
    element.type = 'application/ld+json';
    element.text = this.responseText;
    document.querySelector('head').appendChild(element);
}
var request = new XMLHttpRequest();
request.onload = appendAnnotation;
//here comes the short URL of your annotation
request.open("get", "https://smtfy.it/r1esOtnkhZ", true);
request.send();
```

JS snippet to inject semantic data with JQuery:
```javascript
//here comes the short URL of your annotation
$.getJSON('https://smtfy.it/r1esOtnkhZ', function (annotation) {
    var element = document.createElement('script');
    element.type = 'application/ld+json';
    element.text = JSON.stringify(annotation);
    document.querySelector('head').appendChild(element);
});
```