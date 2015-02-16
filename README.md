# Visual Component Library

Modular and extensible CSS library for Web development today and tomorrow –
the era of component-based Web application development.

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

## Getting Started

See [Tutorial](https://github.com/vcl/doc/tree/master/tutorial)

## Features

- Designed to style [Web Components](http://webcomponents.org/).
- JS framework agnostic ‒ use it with Ember, Angular, you name it.
- For ambitious mobile and desktop applications.
- Complete [set of modules](https://github.com/vcl)
  to handle the bulk of styling needs.
- Customizable through ~500 variables.
- Extensible through custom modules.
- As lightweight as you want ‒ include only what you need.
- Quick rendering through simple, low specificity selectors.
- Maintainable & readable code with unabstracted, obvious naming conventions.
- Relative units like `em` (Elements) are used wherever feasible.
- Powered by the [rework](https://github.com/reworkcss)
  and [npm](https://www.npmjs.org/) eco systems.
- CSS level 4 features like the
  [color-function](http://dev.w3.org/csswg/css-color/#modifying-colors).
- Browsers compatibility is delegated to
  [Autoprefixer](https://github.com/postcss/autoprefixer).

## Guidelines for writing Modules

### Layout

Just see [vcl-list](https://github.com/vcl/list) as a prototype.

### package.json

Have an `index.styl` or `index.css` file per module which is referenced in
the `package.json` in the `style` property.

Have the following custom fields in the package.json file:

- `style` points to the entry CSS file of the module.
- `vcldoc.prio` the priority of the module within its category.
- `vcldoc.category` the main category of the component.
- `vcldoc.categoryPrio` the priority from 1..100 of this category.
- `vcldoc.subCategory` its sub category.
- `vcldoc.subCategoryPrio` the priority from 1..100 of this sub category.

The categorization is used for the documentation generator
[doc-gen](https://github.com/vcl/doc-gen) to generate a static documentation
including samples of your modules.

### CSS Syntax

Use the [white space significant syntax](https://www.npmjs.org/package/css-whitespace)
or plain CSS. Normal CSS files end with the `.css` suffix, white space files
end with the `.styl` suffix.

### Selectors, Naming and Rules

Do’s:

- `vcl` name space prefix for any class name.
- Class names in camelCased letters (why? because it's easier to read and
  shorter than dashes).
- Have a single class name like `vclFlipSwitch` on the root element of the
  corresponding HTML.
- Use relative units like `em`, `rem` etc.
- Descendants names: Apply the same naming conventions; i. e.
  `vclDescendantName`.
- Modifier names: `vclModifierName`.
- In order to prevent class name collisions for descendants and modifiers,
  use an abbreviation of the component’s name, e. g. `vclFSModifier`.

Don’ts:

- No element ID based selectors.
- Avoid element name bound selectors;
  i. e. don’t do `div.header` or `h1.title`.
- Except in rare cases, avoid the descendant selector with elements;
  i. e. don’t use `.vclComponent h3`.
- Except in some very rare cases, avoid using `!important`.
- Don't use vendor prefixes.

### Usable CSS Features

Use the [flexbox based layout attributes](https://github.com/vcl/layout)
to lay out stuff.

### HTML Sample Snippets

- Have a folder `demo` containing a file `example.html` and optionally more snippets.
- Snippet file must be HTML fragments without head and body tags.

## Demo

For every module, you can do an `npm install` and `npm test` to see it.

## Browser Compatibility

Compatibility depends on each module and the use of the
[Autoprefixer](https://github.com/postcss/autoprefixer).

In general, at least the following should be supported and tested:

- Reasonably recent Firefox builds,
- Safari 6+,
- Internet Explorer 10+,
- Reasonably recent Webkit/ Blink engines and derivatives.

## Related Tools

A similar and partly compatible approach is pursued by:

- atomify-css
- suitcss

## Contributing

PRs are welcome!
