---
title: Theme UI
tags:
  - react
emoji: 🎨
link: https://theme-ui.com
---

## Theme spec

https://theme-ui.com/theme-spec

## JSX pragma and the `sx` prop

https://theme-ui.com/sx-prop

```jsx
/** @jsx jsx */
import { jsx } from 'theme-ui'
```

## Packages and methods

### useThemeUI

https://theme-ui.com/use-theme-ui

```js
import { useThemeUI } from 'theme-ui'

export const MyComponent = () => {
  const { theme, colorMode, setColorMode } = useThemeUI()
  return <pre>{JSON.stringify(theme, null, 2)}</pre>
}
```

## Using custom theme object values in `sx` prop

Use the `variant` key as documented [here](https://theme-ui.com/theme-spec#variants).

```jsx
// your theme object
const theme = {
  motion: {
    defaultTransition: {
      transition: 'all 300ms ease-in-out',
    },
  },
}

// use the `variant` key
const Link = () => <a sx={{ variant: 'motion.defaultTransition' }}>Click me</a>

// could also do this
const Link = () => (
  <a sx={{ transition: (theme) => theme.motion.defaultTransition.transition }}>
    Click me
  </a>
)
```

### @theme-ui/color

https://theme-ui.com/packages/color

```js
/** @jsx jsx */
import { jsx } from 'theme-ui'
import { darken, lighten } from '@theme-ui/color'
export default (props) => (
  <div
    {...props}
    sx={{
      color: darken('primary', 0.25),
      bg: lighten('primary', 0.875),
    }}
  />
)
```

## Tips

### Object styles

- https://theme-ui.com/guides/object-styles
- https://emotion.sh/docs/object-styles

#### Reference the theme within

```js
{
  mx: theme => `-${theme.space[2]}`,
},
```

#### [Pseudo elements](https://theme-ui.com/guides/object-styles#pseudo-elements)

```js
{
  "::before": {
    content: '""',
    display: 'block',
    width: 32,
    height: 32,
    backgroundColor: 'tomato',
  }
}
```
