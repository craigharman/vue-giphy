# vue-giphy
Load a random giphy image based on search query

## Installation

``` bash
# install with npm
npm install vue-giphy --save
```

``` javascript
var VueGiphy = require('vue-giphy')
Vue.use(VueGiphy)
```

## Usage

Add as a component:

``` javascript
components: {
    VueGiphy
}
```
You can then show a GIF with:

``` html
<giphy query="<searchQuery>" apiKey="<yourGiphyAPIKey>"></giphy>
```

Replace <searchQuery> with the phrase you want to show a GIPHY for.
Replace <yourGiphyAPIKey> with your API key which can be obtained from  [giphy developers site](https://developers.giphy.com/)

A GIF will appear using the query string provided wherever you place the component.
