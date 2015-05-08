# [VCL](https://github.com/vcl/doc) tutorial

A short tutorial how to build a VCL distribution based on the collection of
[core modules](https://github.com/vcl/core-modules)
and how to style a web page with it.
Plus how to run a single component demo.

## How to build a VCL Distribution

Based on [a blog](http://blog.alex-rudenko.com/2014/08/18/getting-started-with-a-new-css-framework-called-visual-component-library-vcl/)

0.  You will need a current version of node.JS and NPM installed
    because all VCL modules are managed through NPM.

1.  Clone the doc repo from Github.

    `$ git clone https://github.com/vcl/doc.git`

2. As you can see the folder contains several files and a folder:
  * `package.json` for this tutorial containing references to all needed VCL modules.
  * `index.html` is an example website, you can use later.
  * `index.styl` is the index file which just includes other modules and files using `@import`.
  * `vcl-override.styl` is a file where one can override default VCL styles.
  * `vcl-var-override.styl` is a file where variables exposed by the VCL modules can be re-defined.

3.  Open a terminal and execute `npm install` from the tutorial folder.
    After that a node_modules folder will appear which will contain all VCL modules specified in the `package.json`.

4.  From the tutorial folder run the VCL preporcessor to build your VCL distro:

    `node ./node_modules/vcl-preprocessor/bin/vcl.js index.styl vcl.css`

    You should see "✔ Succesfully compiled input to vcl.css" in the terminal if everything is fine.


## Styling a Web Page with the VCL

At this point, you should already have a functional page. If you open the index.html, while the file vcl.css
is in the same directory, you should see an example blog-page.

![picture alt](http://blog.alex-rudenko.com/images/blog_vcl.png)

Explanation of index.html:
First, we include our compiled version of VCL using:
```
<link rel="stylesheet" href="vcl.css">
```
Using the CSS class `vclGridRow` we define a new row of our layout. Class `vclVAlignMiddle` specifies the vertical alignment in the middle
Using the CSS class `vclGridSpan-3` we define that the element will take 3/15 of the page width.
This kind of classes is typical for fluid-grid CSS frameworks. The layout grid module has a total of 15 columns.
We define a horizontal menu on the top of the page using the `vclHorizontalNav` class:
```
<nav id="nav" class="vclHorizontalNav vclHorizontalNavLight" role="navigation">
```

We define a tree (sidebar) navigation using the vclTreeNav class:
```
<nav id="nav" class="vclTreeNav vclTreeNavLight" role="navigation">
```

To define search box we use the vclInputGroup component:
```
<div class="vclInputGroup">
    <input autocomplete="off" type="text">
    <span class="vclInputGroupButton"><button class="vclButtonStd vclSquare"><span><i class="fa fa-search"></i></span></button></span></div>
</div>
```

Now we've learned how to get started with VCL.
Read more about properties and configuration options of each one of the VCL
modules on [GitHub](https://github.com/vcl/vcl).


## How to run a Component Demo

Based on [a blog](http://blog.alex-rudenko.com/2014/09/21/learning-vcl-how-to-build-a-vcl-component-demo/)

You might want to know what a component might look like.
There for you can build a component demo.
In this tutorial we will build a demo for vcl-gallery.
It should already be installed, if you did the previous tutorial.
If not, run:

```
npm install git://github.com/vcl/gallery.git
```

0.  Switch to the directory of the component, you want to build. For this example switch to either
    `../tutorial/node_modules/vcl-core-modules/node_modules/vcl-gallery/`
    or
    `../tutorial/node_modules/vcl-gallery`

1.  Now build the sub-packages needed for building a demo. Since these are devDependencies they are not automatically build in sub-folders.
    To build the demo, run from vcl-gallery:

    `npm install`

2.  After installing the required packages, run from vcl-gallery:

    `npm start`

    If it was successful, you should now have a folder build in vcl-gallery.
    You can now access the demo on [localhost](http://localhost:8077/example.html).

