# CSSium

## Intro

A minimal CSS framework with default styling I keep reusing across multiple
sites. It is intended to be used in content-heavy contexts, like a blog or
documentation.

I am extracting this as I go, rather than trying to author a perfect framework,
so YMMV etc etc.

## Philosophy

- Provide minimal but useful defaults to style the most commonly used bare HTML
  elements that Markdown supports (both
  [CommonMark](https://spec.commonmark.org/0.31.2/) and [GitHub Flavoured
  Markdown](https://github.github.com/gfm/)). I haven't been _pedantically_
  complete, but similar in spirit to many other "classless" frameworks (eg
  [Sakura](https://oxal.org/projects/sakura/),
  [Simple.css](https://simplecss.org)), the idea is you can drop this CSS onto
  nothing but semantic HTML and get legible results out of the box.
- Provide styling for the output of commonly-used plugins. Since I use
  [Eleventy](https://www.11ty.dev/) and various plugins for typography across
  multiple sites, this feels safe to do. Sometimes that output is also bare HTML
  (eg `<sup>`, `<abbr>`, or `<mark>`), and sometimes that involves classnames (eg
  `.ha-placeholder`, `.footnote-ref`, `.token`, or `.admonition`). (Note that I
  _may_ evolve this framework to work in other places that handle Markdown like
  [Obsidian](https://obsidian.md), where I also have [custom
  styling](https://github.com/dlimeb/dotfiles). The plugins and thus classnames
  will differ, but the intent and styling are very similar.)
- Provide helpful utility classes for very common needs like a basic grid,
  visually hiding elements, etc.
- Variable names are _not_ currently namespaced (though I might at some point).
- Classnames this framework exposes are namespaced with `.u-` so I can tell
  where they came from. (I have _no_ intention to evolve this to a utility-first
  style like [Tailwind](https://tailwindcss.com/); those frameworks have their
  place and are excellent at what they are, but in general I'm not a fan of this
  philosophy.) Is my naming scheme/philosophy perfectly consistent? Probably not.
- The `extras` directory contains CSS for commonly used elements that are not
  possible with Markdown, like buttons. I may eventually add support for other
  interactive HTML elements (eg form elements). This framework is meant to be a
  starting point for _written content_, but with some additional inclusions like
  this it can also be helpful in places like small applications or a website with
  a contact form.

## Elements

### Color

The general requirements/thinking behind the palette included here:

- Keep this somewhat neutral, not flavourful. I use this as a base for several
  projects, including some that I don't want a personal "style" on
- Need both Slate and Gray for various neutral or UI elements. Need Red,
  Yellow, Green, Blue for standard UI feedback usage (ie error, warning, success,
  info). Need other hues for cosmetic flexibility.
- That said, intenionally limit the number of additional hues. I don't want a
  very flexible and expressive palette with eg several shades of blue; I want
  just enough to solve common scenarios, but to also make choices quickly and
  keep focused on bigger concerns. Litmus test: common names ("purple", "blue")
  are good, avoid nuanced names ("fuscia", "sky". Exception for "lime" for
  obvious reasons lol)
- Hues and shades are balanced optically, not mathematically. Hues should be
  sufficiently far apart from one another to feel different at a glance.
- Should be usable for both light and dark modes
- Should be usable for syntax highlighting in code blocks
- Should pass WCAG 2.0 AA contrast of 4.5:1 for common scenarios

The above may evolve as I build this and work with it.

Inspiration: [Tailwind](https://tailwindcss.com/docs/colors),
[Catppuccin](https://github.com/catppuccin),
[Flexoki](https://stephango.com/flexoki)

### Typography

Set defaults for:

- Font family, using [browser defaults](https://modernfontstacks.com)
- A fluid font sizing scale ([source](https://utopia.fyi/type/calculator/)

### Layout

Set defaults for:

- A fluid spacing system ([source](https://utopia.fyi/space/calculator/))
- A container for general page dimensions
- A fluid grid system ([source](https://utopia.fyi/grid/calculator/))

### Utilities

Small helper classes that do specific and portable things.

### Content

There is styling here for several categories of HTML elements:

- The `<body>` tag, to establish sensible defaults for type and color
- Bare HTML elements,like `<p>`, `<ul>`, or `<img>`
- The output of commonly-used plugins

## TODO

- Add a test markdown HTML page
