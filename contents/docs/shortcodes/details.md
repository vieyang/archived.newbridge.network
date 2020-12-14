# Details

Details shortcode is a helper for [HTML Details Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details).

- `title` is used for the contents of `summary` tag in details element.

- `open` is used for the attribution of the details element. Specify the initial status of the details element.

## Code Example

```tpl
{{</* details "Title" [open] */>}}
## Markdown content
Lorem markdownum insigne...
{{</* /details */>}}

{{</* details title="Title" open=true */>}}
## Markdown content
Lorem markdownum insigne...
{{</* /details */>}}
```

### Previews

{{< details title="This will be closed by default" >}}

#### Markdown content

Lorem markdownum insigne...
{{< /details >}}

{{< details "This is Opened by default" open >}}

#### Markdown content

Lorem markdownum insigne...
{{< /details >}}
