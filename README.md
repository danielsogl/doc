# Visual Component Library

Extensible, responsive CSS toolkit based on
[OOCSS](https://github.com/stubbornella/oocss/wiki)
principles for now – the time of component-based web
application development.

VCL components can be used selectively and will pull in
dependent modules as required.
There is quite a range of [existing modules](https://github.com/vcl/)
which as a whole should roughly match what Bootstrap offers.
There are very generic, highly reusable styles such as
a typography module and rather specific ones like a product list.
Own components can easily be created as NPM modules and
VCL components can be used together with similar collections
like [SUITCSS](https://github.com/suitcss).

## Status

You can use it productively already if you are comfortable
with changing some variable names (which can be concerned as
the interface of components at build time) in the future.

## Features

- Compatible with the set of browsers you specify.
- Complete [set of modules](https://github.com/vcl)
  to handle the bulk of styling needs.
- Customizable through variables.
- Extensible through own modules.
- As lightweight as you want through modularization.
- Performant through simple, low specificity selectors.
- Maintainable & readable code with unabstracted, obvious naming conventions.
- Relative units like `em` (Elements) are used.
- Powered by the [rework](https://github.com/reworkcss)
  and [npm](https://www.npmjs.org/) ecosystems.
- CSS level 4 features like the
  [color-function](http://dev.w3.org/csswg/css-color/#modifying-colors).

## Guidelines for writing Modules

### Layout

- Just see [vcl-list](https://github.com/vcl/list) as a prototype

### package.json

Have the following custom fields in the package.json file:

- `style` points to the entry CSS file of the module.
- `vcldoc.prio` the priority of the module within its category.
- `vcldoc.category` the main category of the component.
- `vcldoc.categoryPrio` the priority from 1..100 of this category.
- `vcldoc.subCategory` its sub category.
- `vcldoc.subCategoryPrio` the priority from 1..100 of this sub category.

The categorization is used for the documentation generator
[vcldoc](https://github.com/vcl/vcldoc) to generate a menu
structure.

### CSS Code

- Use the [white space significant syntax](https://www.npmjs.org/package/css-whitespace) or plain CSS.
- Normal CSS files end with the `.css` suffix, white space files end with the `.styl` suffix.
- Have an `index.styl` or `index.css` file per module which is referenced in the `package.json` in the `style` property.

### CSS Style

- Avoid the descendant selector with elements (i. e. don’t use `.vclComponent h3`).
- Avoid IDs as selectors.
- Avoid attaching classes to elements in your CSS (i. e. don’t do `div.header` or `h1.title`).
- Except in some rare cases, avoid using `!important`.
- Use relative units like `em` or `rem`.
- You should use the `vcl` name space prefix for any class.
- You should put class names in camelCased letters.

### CSS Features

- Use flexbox based layouts when sensible.
- Stick to the browser compatibility list below.

### HTML Sample Snippets

- Have a folder `demo` containing a file `example.html` and optionally more snippets.
- Snippet file mist be HTML fragments without head and body tags.

## Demo

TODO

## Browser Compatibility

- Firefox,
- Safari 6+,
- Internet Explorer 9+,
- Reasonably recent Webkit engines and derivatives like Blink.

## Related Tools

A similar and partly compatible approach is pursued by:

- atomify-css
- suitcss

## Contributing

PRs are welcome!
