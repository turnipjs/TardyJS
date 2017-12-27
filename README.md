# Tardy.JS
A modular framework for templating HTML, CSS, and JS.

# Please note: this is not actually production ready, documentation in this readme is mostly speculation and planning of features.

---

## About
The purpose of Tardy is to easily manage and modify modular HTML, CSS, and JS components and functionality. This means that the components should be small, interchangable elements that you can combine into one coherent page at least to the degree required by your particular site.

For example, a site with many different pages that all have some common elements with eachother, but are arranged differently or have some variation would benefit from this framework.

Tardy is only a page setup tool, and therefore will only run once (at page load). If you want to create dynamic layouts, you can also use something like CSS Grid (Recommended, since its a pure CSS solution, and therefore can be easily and intuitively included in a collection.) in addition to Tardy.

---

## Setup
1. Download the latest version of `Tardy.js`.
2. Place the file in your public directory.
3. Start your pages with this snippet:
```html
  <!DOCTYPE html>
  <html>
    <head>
      <meta charset="utf-8">
      <script src="[site].tardy.js" charset="utf-8"></script>
    </head>
    <body>
      <div id="content">
      <-tardy >
        
      </div>
      
      <script type="text/javascript">
        // Page declaration and setup
        const page = {
          title: "title",
          collections: ["std"]
        };
        
        tardy();
      </script>
    </body>
  </html>
```
4. Create a tardy template script ex. `myCoolSite.tardy.js` with this snippet:
```javascript
  const collections = {
    _: function() {
      this.header = `
        
      `,
      html-footer:`
      
      `,
      css-:`
      
      `,
      js-: ["path/url"]
    },
    std: {
      
    }
  };
```
5. 🎉**Get Creating!!** 🎉

---

## Creating Your Own Templates
This section takes you through creating your own templates with provided functionality and also provides insight in to how one might go about implementing their own functionalities (Pull requests for functionalities that you may develop are greatly appreciated).

### The Global Collection
The **Global Collection**, which is a user-defined global scope collection, is the most general collection for a site, and as such, ***every site shoud have one***. The scope of this collection is **Global** and therefore will be applied to **every page** before **Specific** collections are applied. At least for now, directly disabling a component of the Global Collection is not possible due to limited applicability.

This collection should contain components such as the CSS with the background and text/button styles that are common to all pages within a website.

### Basic Collections
Basic collections are user-difined specific scope collections that must be included in a page by name.

### The basics
To best understand how to make your own websites with Tardy.js, it is important to know the Tardy.js system. You first make 

---

## Scopes and the Collectioning Order

### Global:
Only the `_` collection will have **Global** scope. During the **Collectioning Process**, the `_` collection will be processed first, before the specific collections are applied.

### Specific:
Any collection that is not specified as global with and underscore at the beginning of its identifier will be considered a specific collection, and therefore must be included by name in the page's `page.collections` definition.

---

## Compatability
Check [caniuse.com](https://caniuse.com/#search=Custom%20Elements%20v1) for the latest compatability stats. (~75% support as of 2017-12-07)  
Note: Tardy does not use Customized Built-In Elements and therefore only requires partial support.

---

## Glossary
#### Tardy:
A modular method of templating HTML, CSS, and JS.

#### Collection:
A set of components that are stored together under one name so as to be applied to a page as a set.

#### Component:
An individual snippet of HTML, CSS, or JavaScript that belongs to a collection.  
Best practicice suggest making them entirely intercompatable if possible.

---

## Future Plans
