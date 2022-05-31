# Snippets

Collecting bits and pieces in one place

## HTML

### Protect target blank from mischief

```
<a href="https://hacks.mozilla.org/2022/04/mdn-plus-now-available-in-more-markets" target="_blank" rel="noopener noreferrer">Learn more</a>
```

## CSS

### Sticky Footer

```
html {
  height: 100%;
}

body {
  height: 100%;
}

footer {
  position: sticky;
  top: 100%;
}
```

### Container Without Inner Div

```
.content {
  padding: var(--gap) max(var(--edge), calc(50% - var(--width-xl)/2);
}
```

### Autogrid

```
.results {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(var(--card-width), 1fr));
    gap: var(--gap);
    max-width: var(--max-width);
    padding: 0 var(--edge);
    margin: 0 auto;
}
```
