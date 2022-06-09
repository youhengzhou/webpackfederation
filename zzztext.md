mfp

module federation plugin

# app1

/ public

- index.html
this file just has the div with id='root' for injections by react

/ src

- App.js
interesting here is the RemoteApp, it imports import('app2/App')

- bootstrap.js
this has nothing of value, it just renders, the index.js in many other cases

- index.js
the actual index.js, imports the app2 url

/

- package.json
the usual, start for serve, build for webpack --mode production

- webpack.config.js
where it gets weird

remotes: {
  app2: "app2@[app2Url]/remoteEntry.js",
},
MOST IMPORTANT PART, COPY THIS PART

shared: {react: {singleton: true}, "react-dom": {singleton: true}},
probably unnecessary


- IMPORTS

ModuleFederationPlugin
the main thing of the plugin

ExternalTemplateRemotesPlugin
idk wtf this shit is








# app2

/ public

- index.html
same thing as app1, id='root' for react to inject







