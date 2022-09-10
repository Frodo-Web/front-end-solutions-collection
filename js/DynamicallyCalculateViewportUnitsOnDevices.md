```JavaScript
document.addEventListener('DOMContentLoaded', setViewportUnits);
window.addEventListener('resize', setViewportUnits);
window.addEventListener('orientationChange', setViewportUnits);

function setViewportUnits() {
  // Viewport height * 1% to get a value for a vh unit
  const vh = window.innerHeight * 0.01;
  // Set the value in the --vh custom property to the root of the document
  document.documentElement.style.setProperty('--vh', `${vh}px`);
}
```

```CSS
elemnt {
  height: 100vh;
  /* Fallback for browsers that don't support custom properties */
  height: calc(var(--vh, 1vh) * 100);
}
``
