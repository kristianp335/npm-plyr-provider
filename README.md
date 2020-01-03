## Dynamic NPM dependency loading in Liferay

This is an example of a npm dependency module. You can call the module by loading via Liferay.Loader. In this example I am loading Plyr but it could be almost any dependency.

You should call your dependency using Liferay.Loader. I am currently calling the dependency module directly due to an issue I am working with alongside the Liferay product team.

It is best to actually call the main js file in the module, but there is an issue with this currently. Here I am just calling the Player AMD module which is the main dependency of the module. This is not ideal, since I don't want the module version to be a issue in future. Keep checking here for updates.

```
Liferay.Loader.require("npm-plyr-provider$plyr@3.5.6/dist/plyr", function(Plyr) {
    console.log(Plyr);
    var player = new Plyr('#player');
    console.log(player)
});

```

Checkout package.json and the babel.rc files for examples of using Liferay bundler and Babel.

**The gradle dependencies in this project are setup for Liferay 7.2, you can amend them for late versions of 7.0, and Liferay 7.1**

