# Mermaid Chart

[Mermaid](https://mermaidjs.github.io/) is library for generating svg charts and diagrams from text.

## Example

{{< columns >}}
```tpl
{{</*mermaid class="text-center"*/>}}
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick
        Bob->>Alice: Not so good :(
    else is well
        Bob->>Alice: Feeling fresh like a daisy
    end
    opt Extra response
        Bob->>Alice: Thanks for asking
    end
{{</*/mermaid */>}}
```

<--->

{{< mermaid >}}
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick
        Bob->>Alice: Not so good :(
    else is well
        Bob->>Alice: Feeling fresh like a daisy
    end
    opt Extra response
        Bob->>Alice: Thanks for asking
    end
{{</mermaid>}}

{{</columns>}}

## Flowchart

```tpl
{{</*mermaid class="text-center"*/>}}
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
{{</*/mermaid */>}}
```

{{<mermaid class="text-center" >}}
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
{{</mermaid>}}

## Sequence diagram

```tpl
{{</*mermaid class="text-center"*/>}}
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
{{</*/mermaid*/>}}
```

{{<mermaid class="text-center">}}
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
{{</mermaid>}}