<h1 align="center">
	<br>
	<img width="60" src="/favicon.svg" alt="theme-toggle">
  <p>theme-toggle</p>
  <span>
	<br>
	<br>
</h1>

> a simple javascript/css solution for toggling light/dark themes on websites

---

## Highlights

- Totally inspired by [Adam Argyle](https://github.com/argyleink) based on his GUI Challenges over at web.dev ([theme switching component](https://web.dev/building-a-theme-switch-component/))
- Simple library
- Links to user **prefers-color-scheme** OS settings
- Writes to browser **localStorage** to remember user preferences

## Install

```sh
npm install @andystevenson/theme-toggle
```

## Usage

```js
import toggle from '@andystevenson/theme-toggle'
```

**.... that's it!**

##### Styling it with CSS

```css
[data-theme='light'] {
  color-scheme: light;
  background-color: antiquewhite;
  color: darkslategray;
}

[data-theme='dark'] {
  color-scheme: dark;
  background-color: darkslategray;
  color: antiquewhite;
}

html[data-theme='dark'] [data-theme='light'].theme-toggle,
html[data-theme='light'] [data-theme='dark'].theme-toggle {
  display: none;
}
```

##### Linking it into your HTML

```html
<head>
  <script type="module" src="./theme-toggle.js"></script>
  <!-- assuming theme-toggler.js would do the following -->
  <!-- import toggle from '@andystevenson/theme-toggle' -->
  ...
</head>
```

The rationale for doing it like this

> _Quoting from Adam Argyle..._<br>
> To achieve this, a plain **<_script_>** tag in the document **<_head_>** is loaded first, before any CSS or **<_body_>** markup. When the browser encounters an unmarked script like this, it runs the code and executes it before the rest of the HTML. Using this blocking moment sparingly, it's possible to set the HTML attribute before the main CSS paints the page, thus preventing a flash or colors.

### Under the covers

To make the toggle work the HTML page must contain a clickable element with **id="theme-toggler"** _(can be anything... even a div)_.

What happens when user clicks/selects the _**theme-toggler**_ is an attribute **data-theme'** is attached to the **<_html_>** document tag. What the **_theme-toggle_** library is doing is switching between **data-theme='dark'** and **data-theme='light'**. How you then style these is up to you. See the trivial CSS above as an example. Have a look at the git hub repo [<img src='./GitHub-Mark-32px.png' width="16">](https://github.com/andystevenson/theme-toggle) for a full example with a working [**index.html**](https://github.com/andystevenson/theme-toggle/blob/master/index.html) example. The **package.json** uses [<img src='https://vitejs.dev/logo.svg' width="16">](https://vitejs.dev/) as the bundler. <br>

## Credits

All credit to [Adam Argyle](https://github.com/argyleink) for the inspiration.

I used a couple of SVG icons from the very useful [Bootstrap Icons Library](https://icons.getbootstrap.com/).

## License

[MIT](LICENSE.md)

## Maintainer

- [Andy Stevenson](https://github.com/andystevenson)
