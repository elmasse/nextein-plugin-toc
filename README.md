# nextein-plugin-toc
Add a Table of Contents as `toc` to your `post.data` based on your post content.


## Install

```
npm i nextein-plugin-toc
```

## Usage

Edit your `next.config.js` file and add it to the plugins list:

```js
// next.config.js
const { withNextein } = require('nextein/config')


module.exports = withNextein({
  nextein: function(config) {
   
    config.plugins.push({
      name: 'nextein-plugin-toc',
    })

   return config
 },
  // ...
}))

```

## Pre-Requisites

In order to get a TOC with `href` values you can use `rehype-autolink-headings` and `rehype-slug` plugins in the `nextein-plugin-markdown` configuration. 

```
npm i rehype-slug rehype-autolink-headings
```

```js

module.exports = withNextein({
nextein: {
    plugins: [
      {
        name: 'nextein-plugin-markdown', 
        options: {
          rehype: [
            'rehype-slug',
            'rehype-autolink-headings'
          ]
        }
      },
      {
        name: 'nextein-plugin-toc',
        options: {
          categories: ['guides', 'docs']
        }
      }
    ]
  }  
})

```

