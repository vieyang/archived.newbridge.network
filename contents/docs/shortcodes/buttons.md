# Buttons

Buttons are styled links that can lead to local page or external link.

## Code Example

```tpl
{{</* button relref="/" [class="..."] */>}}Get Home{{</* /button */>}}
{{</* button href="https://github.com/" */>}}Contribute{{</* /button */>}}
```

### Button for relative URLs

{{< tabs "relative" >}}
{{< tab "Code" >}}

```tpl
{{</* button relref="/" */>}}Go Home{{</* /button */>}}
```

{{< /tab >}}

{{< tab "Result" >}}

{{< button relref="/" >}}Go Home{{< /button >}}

{{< /tab >}}
{{< /tabs >}}

### Button for external URLs

{{< tabs "external" >}}
{{< tab "Code" >}}

```tpl
{{</* button href="https://newtonproject.org" */>}}Newton Project{{</* /button */>}}
```

{{< /tab >}}

{{< tab "Result" >}}

{{< button href="https://newtonproject.org" >}}Newton Project{{< /button >}}

{{< /tab >}}
{{< /tabs >}}
