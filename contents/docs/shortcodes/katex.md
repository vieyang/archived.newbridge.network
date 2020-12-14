# KaTeX

KaTeX shortcode let you render math typesetting in markdown document.

See [KaTeX](https://katex.org/) for more.

## Code Example

{{< columns >}}

```latex
// Simple One

{{</* katex [display] */>}}\pi(x){{</* /katex */>}}

// Let's do formula

{{</* katex [display] */>}}
f(x) = \int_{-\infty}^\infty\hat f(\xi)\,e^{2 \pi i \xi x}\,d\xi
{{</* /katex */>}}

// Let's get complicated

{{</* katex [display] */>}}
\frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} = 1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}} {1+\frac{e^{-8\pi}} {1+\cdots} } } }
{{</* /katex */>}}

```

<--->

**Simple One**

{{< katex display >}}\pi(x){{< /katex >}}

**Let's do formula**

{{< katex display >}}
f(x) = \int\_{-\infty}^\infty\hat f(\xi)\,e^{2 \pi i \xi x}\,d\xi
{{< /katex >}}

**Let's get complicated**

{{< katex display >}}
\frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} = 1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}} {1+\frac{e^{-8\pi}} {1+\cdots} } } }
{{< /katex >}}

{{< /columns >}}

## Display Mode

The default display mode is _inline_. You can put any `katex` inline witht the text. Taking {{< katex >}}\pi(x){{< /katex >}} for example.

When `display` attribute is set. The `katex` element itself will be set with a `display: block` CSS style.
