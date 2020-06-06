---
path: awesome-images
date: 2020-06-06T00:26:57.404Z
title: Awesome Images
description: Fix for gatsby-plugin-mdx and gatsby-remark-images
---
![great gatsby]( "great gatsby")

From \[@cwgw](https://github.com/cwgw)...

So digging a little deeper, it looks like Gatsby only looks for "subplugins" at one specific path, \`options.plugins\`.

\`gatsby-plugin-mdx\` uses \`options.gatsbyRemarkPlugins\`. This is fine for transforming markdown as the plugin handles that itself, but Gatsby-specific api files like \`gatsby-browser.js\` don't get loaded because Gatsby doesn't know they exist.

If you try this…

\`\``javascript

\    {

\    resolve: 'gatsby-plugin-mdx',

\    options: {

\    gatsbyRemarkPlugins: \[ \`gatsby-remark-images\` ],

\    plugins: \[ \`gatsby-remark-images\` ],

\    }

\    },

\`\``

…everything works as it should.
