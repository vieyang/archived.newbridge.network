# Columns

Columns help organize shorter pieces of content horizontally for readability.

## Code Example

The following short code will be displayed as a `3 columns` layout in wide screen.

```html
{{</* columns */>}} <!-- begin columns block -->

### Left Content
Lorem markdownum insigne...

<---> <!-- magic separator, between columns -->

### Mid Content
Lorem markdownum insigne...

<---> <!-- magic separator, between columns -->

### Right Content
Lorem markdownum insigne...

{{</* /columns */>}} <!-- end columns block -->
```

## Preview

Here's what will look like for the code above.

{{< columns >}}

### Left Content

Lorem markdownum insigne. Olympo signis Delphis! Retexi Nereius nova develat
stringit, frustra Saturnius uteroque inter! Oculis non ritibus Telethusa
protulit, sed sed aere valvis inhaesuro Pallas animam: qui _quid_, ignes.
Miseratus fonte Ditis conubia.

<--->

### Mid Content

Lorem markdownum insigne. Olympo signis Delphis! Retexi Nereius nova develat
stringit, frustra Saturnius uteroque inter!

<--->

### Right Content

Lorem markdownum insigne. Olympo signis Delphis! Retexi Nereius nova develat
stringit, frustra Saturnius uteroque inter! Oculis non ritibus Telethusa
protulit, sed sed aere valvis inhaesuro Pallas animam: qui _quid_, ignes.
Miseratus fonte Ditis conubia.
{{< /columns >}}
