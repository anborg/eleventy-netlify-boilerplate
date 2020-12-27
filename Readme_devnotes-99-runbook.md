
# A 11ty Demo site -me 


# setup new

```
SET PROJ_NAME=eleventy-site
mkdir %PROJ_NAME%
cd %PROJ_NAME%
npm init -y
npm install @11ty/eleventy @11ty/eleventy-plugin-vue --save
```

Create 11nty config js 

```
cat <<EOT >> .eleventy.js
const eleventyVue = require("@11ty/eleventy-plugin-vue");

module.exports = function(eleventyConfig) {
  eleventyConfig.addPlugin(eleventyVue);
};

EOT
```


create a Vue single file component.
```
cat <<EOT >> index.html

<template>
  <html lang="en">
    <head>
      <meta charset="utf-8">
      <title>Demo: Vue and Eleventy</title>
    </head>
    <body>
      <p>Hello from Vue.</p>
      <p>Hello from Eleventy.</p>
    </body>
  </html>
</template>
<script>
export default {
  components: {}
}
</script>
```

Run 
```
set ELEVENTY_EXPERIMENTAL=true 
npx @11ty/eleventy --serve
```