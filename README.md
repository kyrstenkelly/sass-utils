# Sass Utils

My go-to variables/mixins/functions in one place for easier re-use.

* [Installation](#installation)
* [Variables](#variables)
* [Functions](#functions)
* [Mixins](#mixins)

## Installation
```bash
npm install -D kyrsten-sass-utils
```

## Variables

### Screen Sizes:
```scss
$screen-xs: 320px;
$screen-sm: 480px;
$screen-md: 768px;
$screen-lg: 992px;
$screen-xl: 1200px;
```

### Font Weights:
```scss
$font-weight-light: 300;
$font-weight-regular: 400;
$font-weight-medium: 500;
$font-weight-semibold: 600;
$font-weight-bold: 700;
```

## Functions

### `rem($px)`
Easy conversion from pixels to rem.

## Mixins

### Media Query 
#### `@media` 
Mixin to facilitate mobile-first media queries. 
```scss
@include media($screem-sm) { ... }
```  
will compile to
```scss
@media only screen and (min-width: $screen-sm) { ... }
```

### Visibility Helpers

Using the sizes listed above (`xs`, `sm`, `md`, `lg`, `xl`), you can use these helper classes to show certain DOM elements for only certain screen sizes.

#### `.show-[size]`
Show only for the given size. Example:  
```html
<div className="show-md">
  Will only appear from 768px to 991px.
</div>
<div className="show-lg">
  Will only appear from 992px to 1199px.
</div>
```


#### `.show-[size 1]-[size 2]`
Show only for a given range. `size-1` must be a smaller size than `size-2`. Example:  
```html
<div className="show-xs-md">
  Will appear on xs, sm and md screens (from 320px to 991px).
</div>
```

#### `show-[size]-up`
Show for the given size and all larger sizes. Example:  
```html
<div className='show-md-up'>
  Will appear on md and all larger sizes (from 768px+).
</div>
```

#### .show-[display]
The display property will default to `block` unless you add one of these classes. Available display options:  
* `flex`
* `inline`
* `inline-block`

Example:  
```html
<div className="show-xs-md show-flex">
  Will appear from xs to md screens and will have "display: flex;".
</div>
```
