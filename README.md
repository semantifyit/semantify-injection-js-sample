# Semantify.it Demo
Demo website for the [semantify.it service](https://semantify.it/). Shows how semantic annotations can be loaded at runtime and be crawled by engines like google's Data Testing Tool or [semantify.it's semantic validator](https://semantify.it/validator/). 

The *index.html* includes the code to dynamically append semantic data from a remote source, eg. semantify.it annotations through the url of the annotation. 

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```