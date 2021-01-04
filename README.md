
# Lazyload

![version](https://img.shields.io/github/manifest-json/v/Natjo/lazyload)

Native lazyload for images.     
Set **width** and **height** for preventing content reflow and maintain **aspect ratio**.

## Usage

### html
```html
<img src="https://picsum.photos/id/400/536/354" loading="lazy" width="536" height="354" alt=""> 
```

### javascript
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

### css
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
