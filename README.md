## Dynamic NPM dependency loading in Liferay

This is an example of a npm dependency module which is Liferay we call a provider. It is useful because you can dynamically add npm dependencies to your Liferay as OSGI modules and then call them asynchronously. You can call the module by loading via Liferay.Loader. In this example I am loading Plyr but it could be almost any dependency.

You should call your dependency using Liferay.Loader. 

```

Liferay.Loader.require("npm-plyr-provider@1.0.0", function(player) {
});
Liferay.Loader.require("npm-plyr-provider$plyr@3.5.6/dist/plyr.css", function(playerCss) {
});

```
Checkout package.json, .babelrc, .npmbundlerrc, and index.js files for examples of using Liferay bundler and Babel.

**The gradle dependencies in this project are setup for Liferay 7.2, you can amend them for late versions of 7.0, and Liferay 7.1**

**TODO - Move the require call for the CSS to an import in the index as opposed to a direct call to the dependency**

