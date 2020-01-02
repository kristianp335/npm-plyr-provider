## Dynamic NPM dependency loading in Liferay

This is an example of a npm dependency module. You can call the module by loading via Liferay.Loader. In this example I am loading Plyr but it could be almost any dependency.

You should call your dependency using Liferay.Loader like this:

```
Liferay.Loader.require("npm-plyr-provider@1.0.0/index", function() {
    alert("plyr was loaded");
});

```

Checkout package.json and the babel.rc files for examples of using Liferay bundler and Babel.

**The gradle dependencies in this project are setup for Liferay 7.2, you can amend them for late versions of 7.0, and Liferay 7.1**

