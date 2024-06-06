<style type="text/css">

.focus {
  color: var(--theme-foreground-focus);
}

.invert {
  background-color: var(--theme-foreground-alt);
  color: var(--theme-background);
}

.crop {
  border-radius: 8px;
  margin: 1rem;
  max-width: calc(50% - 2rem);
  box-shadow: 0 0 0 0.75px rgba(128, 128, 128, 0.2), 0 6px 12px 6px rgba(0, 0, 0, 0.4);
  aspect-ratio: 3024 / 1888;
  object-fit: cover;
  object-position: 0 100%;
}

.wbr::before {
  content: "\200b";
}

.wide {
  max-width: 960px;
}

figcaption code {
  font-size: 90%; /* TODO move to global.css */
}

h2 {
  margin: 1.5rem 0 1rem 0;
  font-size: 2rem;
}
.margin-note {
    width: 200px;  /* Set the width of the image */
    float: right;  /* Align the image to the right */
    margin-left: 20px; /* Space between the text and the image */
    margin-right: -280px; /* Pull the image into the right margin */
    position: relative; /* Position relative to its normal position */
    top: 0; /* Align the top of the image with the top of the paragraph */
    box-shadow: 0 0 0 0.75px rgba(128, 128, 128, 0.2), 0 6px 12px 6px rgba(0, 0, 0, 0.4);
}
.model-container {
    margin: 1.5rem 0 1rem 0;
    position: relative;
    border: 1px solid black;
    border-radius: 6px;
    box-shadow: 1px 1px 30px rgba(252, 220, 252, 1);
  }

</style>

# The best DAWGS


Statistical model as golem is a great metaphor because it forces you to think from the model's perspective. Similar to when we 
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9f/Prague-golem-reproduction.jpg/440px-Prague-golem-reproduction.jpg" alt="golem wiki" class="margin-note"/>debug, the first step is to realize that the unwanted behaviors might not be a bug but exactly what you are asking for.

Note. By clicking on the headers, you'll be sent to the corresponding location in the lectures.

## [Context & discrimination](https://www.youtube.com/watch?v=Zi6N3GLUJmw&list=PLDcUM9US4XdPz-KxHM4XHt7uUVGWWVSus&index=9&t=4432s)

```js
mermaid`
graph LR
    X[Status] --> Z(Context)
    Z --> Y[Event]
    X --> Y
    style X fill:#fff, stroke-width:0px
    style Y fill:#fff, stroke-width:0px
    style Z fill:#fff, stroke-width:0px
`
```  

For instance, in the Berkeley admission problem, we get that women might choose departments that are more competitive (think maths vs. psychology at graduate level), and maybe there is also a gender bias:

```js
mermaid`
graph LR
    X[Gender] --> Z[Department]
    Z --> Y[Admission]
    X --> Y
    style X fill:#fff, stroke-width:0px
    style Y fill:#fff, stroke-width:0px
    style Z fill:#fff, stroke-width:0px
`
```

The gender bias is confounded by department choice. Or, more controversially

```js
mermaid`
graph LR
  u((hidden quality))
  X[Gender] --> Z[Department]
  Z --> Y[Admission]
  X --> Y
  u -.-> Y
  u -.-> Z
  style X fill:#fff, stroke-width:0px
  style Y fill:#fff, stroke-width:0px
  style Z fill:#fff, stroke-width:0px
  style u fill:#fff, stroke-dasharray: 5 5
`
```  

---

## [Varying confound](https://www.youtube.com/watch?v=sgqMkZeslxA&list=PLDcUM9US4XdPz-KxHM4XHt7uUVGWWVSus&index=13)

```js
mermaid`
graph LR
  U((Neighborhood))
  U --> Z
  U -->Y
  Z --> Y[Children]
  X[Granparents] --> Z(Parents)
  X --> Y
  style X fill:#fff, stroke-width:0px
  style Y fill:#fff, stroke-width:0px
  style Z fill:#fff, stroke-width:0px
  style U fill:#fff, color:#AA4A44, stroke:#AA4A44, stroke-dasharray: 5 5
  linkStyle 1 stroke:#AA4A44
  linkStyle 0 stroke:#AA4A44
`
```  

It is similar to context & discrimination, but here we have a _collider_. For instance, in the children education problem, parents influence children outcome. But grand parents and neighborhod (a proxy for socioeconomic status), also influence children outcome AND parents. Similarly, one could see the following model of becoming a National Academy of Science, given citation patterns, gender, and hidden quality of the works:

```js
mermaid`
  graph LR
  X[Gender]
  Y[Citations]
  Z[NAS member]
  U((quality))
  U --> Y
  U --> Z
  Y --> Z
  X --> Y
  X --> Z
  style U fill:#fff, color:#AA4A44, stroke:#AA4A44, stroke-dasharray: 5 5
  linkStyle 1 stroke:#AA4A44
  linkStyle 0 stroke:#AA4A44
  style X fill:#fff, stroke-width:0px
  style Y fill:#fff, stroke-width:0px
  style Z fill:#fff, stroke-width:0px
`
```  

---

## [Oceanic tool](https://www.youtube.com/watch?v=jokxu18egu0&list=PLDcUM9US4XdPz-KxHM4XHt7uUVGWWVSus&index=10)

```js
mermaid`
graph LR
    X[Population]
    Y[Tools]
    Z[Contact]
    L[Location]
    X --> Y
    X --> Z
    L --> X
    L --> Z
    L --> Y
    Z --> Y
    style L fill:#fff, stroke-width:0px
    style X fill:#fff, stroke-width:0px
    style Y fill:#fff, stroke-width:0px
    style Z fill:#fff, stroke-width:0px
`
```  

---

## [Survival Analysis](https://www.youtube.com/watch?v=Zi6N3GLUJmw&list=PLDcUM9US4XdPz-KxHM4XHt7uUVGWWVSus&index=9)

```js
mermaid`
graph LR

`
``` 

---

## Got milk? multicollinearity example (rethinking p.173)

```js
mermaid`
graph LR
  L((Lactose))
  F[[Fat]]
  K
  L --> K
  D --> L
  D --> F
  F --> K
  style D fill:#fff, color:#AA4A44, stroke:#AA4A44, stroke-dasharray: 5 5
  linkStyle 1 stroke:#AA4A44
  linkStyle 0 stroke:#AA4A44
  linkStyle 3 stroke:#AA4A44
  linkStyle 2 stroke:#AA4A44
  style L fill:#fff, stroke-width:0px
  style K fill:#fff, stroke-width:0px
  style F fill:#fff, stroke-width:0px
`
``` 
