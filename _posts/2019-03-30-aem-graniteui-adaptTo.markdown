---
layout: post
title:  "AEM Granite UI adaptTo"
date:   2019-03-29 16:02:15
categories: AEM
---
# AEM Granite UI adaptTo

Any developer working on AEM is very much familiar with [Sling Adapter](https://sling.apache.org/documentation/the-sling-engine/adapters.html) design pattern and the famous adaptTo calls.

But you may not be aware the same pattern is used by Granite UI javascript. You can read more about it on [Granite Documentation](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/coral/foundation/clientlibs/foundation/js/adapter/index.html)

With this you can easily adapt a standard jQuery element to a Granite field object.

For example - if you have comma separated values in JavaScript Code and want to initialize MultiField TouchUI component with those values.
Then you simply have to write the following lines of code-

```
    var field = $("[data-granite-coral-multifield-name='./jcr:content/metadata/dam:search_promote']")
    var graniteField = field.adaptTo("foundation-field");
    graniteField.setValues(["one","two","three"]);
```

The above code is fetching the multifield using the standard jQuery code. And then we adapt the element to "foundation-field" element which is the standard adapter for all Granite UI field components.

And then we make a call to the standard methods like setValues which takes care of initializing the field with the given values.
You don't have to write additional JS code to manipulate DOM and handle all the scenarios of refreshing the field UI yourself.

Check the documentation of "foundation-field" [Adapter interface](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/coral/foundation/clientlibs/foundation/vocabulary/field.html)

 As per the documentation the adapter returns FoundationField adapted object for all field elements.

 Similarly there are other adapter types like [Foundation Collection](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/coral/foundation/clientlibs/foundation/vocabulary/collection.html)

 The condition for foundation-collection adapter is that the element should have the css class ".foundation-collection".

 Next time you work on Touch UI components in JavaScript code, make sure to use the adaptTo pattern which will lead to less and efficient code.

 Hope this tip will help you in touch ui development.
 Happy coding!