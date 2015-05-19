# Visual Component Library

Modular and extensible CSS library for Web development today and tomorrow –
the era of component-based Web application development.

VCL components can be used selectively and will pull in
dependent modules as required.
There is quite a range of [existing modules](https://github.com/vcl/).
The collection of
[core modules](https://github.com/vcl/core-modules)
roughly provide what Bootstrap offers.
There are very generic, highly reusable styles such as
a typography module and rather specific ones like a process navigation.
Own components can easily be created as NPM modules.

## Status

We have reached a **0.1.0 version level** and adhere to
[semver](http://semver.org/). So you can use it productively.

## Getting Started

See the [tutorial](https://github.com/vcl/doc/tree/master/tutorial) on
how to build a distribution.

There is a [presentation](http://vcl.github.io/presentation/index.html)
introducing the VCL.

## Features

- Designed to style [Web Components](http://webcomponents.org/).
- JS framework agnostic ‒ use it with EmberJS, Angular, you name it.
- For ambitious mobile and desktop applications.
- Collection of [core modules](https://github.com/vcl/core-modules)
  to handle the bulk of styling needs.
- [Default theme](https://github.com/vcl/default-theme)
  for core modules with ~500 variables.
- Themes are modules on its own but they can inherit from each other.
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

### Structure

Just see [vcl-list](https://github.com/vcl/list) as a prototype.

### package.json

Have an `index.styl` or `index.css` file per module which is referenced in
the `package.json` in the `style` property.

Have the following custom fields in the `package.json` file:

- `style` points to the entry CSS file of the module.
- `vcl.categories` an array of categories. Example: `{ "title": "Icons", "ItemPriority": 30, "priority": 140}`
  - `category.title` - The title of the category.
  - `category.priority` - The priority of the whole category. Determines where the Menu entry is ordered.
  - `category.ItemPriority`- Priority of the Item. Determines the display order of this module in its category.
- `vcl.needs` Specifies what providers this module needs. (Most modules will need a `theme` provider.)
- `vcl.provides` Providers of this module. Examples: `theme`, `theme-terms`, `button`

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
to realize complex layouts.

### HTML Sample Snippets

- Have a folder `demo` containing a file `example.html` and optionally more
  snippets.
- Include multiple demos using HTML imports `<link rel="import"...`.
- Snippet file must be HTML fragments without head and body tags.

### Development

The following npm scripts are available:

* `npm start` - starts a web server and opens the examples (auto-reloads).
* `npm test` - tries to pre-process the code.

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

- [atomify-css](https://github.com/atomify/atomify-css),
- [SUITCSS](https://github.com/suitcss).

## Contributing

PRs are welcome!
