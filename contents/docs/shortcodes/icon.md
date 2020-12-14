# Icon Shortcode

We've intergrated [Bootstrap Icons](https://icons.getbootstrap.com) for using vector icons in the website.

## Code Example

```tpl
{{</* icon icon=[iconname] class=[classname] color=[color] */>}}
```

This will create a _svg_ element like:

```html
<svg class="icon classname" color="color">
  <use xlink:href="/icons/bootstrap-icons.svg#iconname"></use>
</svg>
```

- `icon` will be the icon you want to use.

- `class` is the class for the _svg_ element.

- `color` is optional, the icon will take the color define by it's parent element. You can set `color` if you want to use a different one.

- The default icon size will take the line-height defined by it's parent element.

## Preview

{{< columns >}}

**Cloud Icon**

```tpl
{{</* icon icon="cloud" */>}}
```

**Red Colored**

```tpl
{{</* icon icon="cloud" color="red" */>}}
```

<--->

**Cloud Icon**

{{< icon icon="cloud" >}}

**Red Colored**

{{< icon icon="cloud" color="red" >}}

{{< /columns >}}
