
# Popin

![version](https://img.shields.io/github/manifest-json/v/Natjo/lazyload)

Native lazyload for images.

## Usage
```javascript
if ('loading' in HTMLImageElement.prototype) {
    document.querySelectorAll('img[loading]').forEach((img) => {
        if (img.complete) img.loading = 'eager';
        img.onload = () => img.loading = 'eager';
    });
} else {
    document.querySelectorAll('img[loading]').forEach((img) => img.removeAttribute('loading'));
}
```

```css
img[loading] {
    opacity: 0;
    height: auto;
    transition: opacity 0.35s ease;
}
img[loading=eager] {
    opacity: 1;
}
```
