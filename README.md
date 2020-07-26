# babel-plugin-transform-scss

Babel plugin for converting scss or sass imports to css and embedding them in the head of the document

This plugin can be used for replacement of `sass-loader`

### How it works

This plugin will convert all scss or sass imports to the standard `<style>` attribute. For example:

```javascript
import React from 'react'
import 'style.scss'

const Button = () => {
  return (
    <div className="button">
      Custom button
    </div>
  )
}

export default Button
```

`import "style.scss"` will be transformed to css and will be added to the `head` of the `document`:

```html
<style data-scss-component="Button_style">
    .button {
      display: flex;
      justify-content: space-around;
    }
</style>
```