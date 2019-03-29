---
layout: post
title:  "AEM Touch UI - How to debug TouchUI components? "
date:   2019-03-29 16:02:15
categories: AEM
---
# AEM Touch UI - How to debug TouchUI components?

As an AEM developer you might have got requirements from the customer to customize the TouchUI. Ideally we generally don't recommend doing any customizations but in some projects you are not left with any choice.
You may be required to do the following

* Add a new icon in the start screen
* Add a new UI action in the TouchUI list view
* Change the label of an action
* Add a new list, column or card view
* Add a render condition to show or hide an action based on a condition

And there can be many other such requirements.

The first thing for you to do Touch UI customization is to find out the container Granite component which you need to overlay and make the changes.
Many developers are not able to easily find out which container component it is and where it exists in the repository heirarchy.

I have seen most of the time devs have to find out what CSS classes are applied on the container component and then search for those class names in the repository.
If you are lucky with the css name then you will see less number of results and you can find out the component. But many times you may see too many results and you are not able to figure out the container component easily.

To solve this problem of component identification in the DOM, I contributed this tool in Adobe ACS Tool project - [Sling Component Debugger](https://adobe-consulting-services.github.io/acs-aem-tools/features/sling-component-debug-filter/index.html)

Using this tool you can easily find out the Touch UI container components by just looking for the following comment in the HTML-

\<!-- acs:resourcePath: /path/to/the/included/resource -->

The tools prints the path of the container component and you can directly use the path to navigate to the touch UI component.

For example, if you are customizing the AEM Start Screen then you can inspect any of the icons shown on the screen and you will see comments like below-

\<!-- {acs:resourcePath:/mnt/overlay/cq/core/content/nav-->

![alt text](https://raw.githubusercontent.com/kunalgaba/kunalgaba.github.io/master/assets/Sling-component-debugger.png "Sling Component Debugger")

So now you know the start screen navigation component in the repository is located at - /libs/cq/core/content/nav.

This tool has helped me save alot of time in my projects.

Hope this will help you in customizing Touch UI.
Install ACS Tools package and start using Sling Component debugger.

Happy coding!




