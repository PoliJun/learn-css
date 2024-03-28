# Other Notes

[code](./pages/overflowhidden.html)

Use elements addEventListener for a button. In case of the function name is already used or is a reserved word.

In this case, scrollLeft is an property of the element, so it is not possible to use it as a function name.

**Fix:**

```javascript
document.querySelector('button').addEventListener('click', function() {
    container.scrollBy({
        left: 100,
        behavior: 'smooth'
});
```
