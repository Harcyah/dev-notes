# How to ... Bookmarklets !

## Extract all h3 tags from a webpage

```javascript
var headers = []; 
document.querySelectorAll('h3').forEach(h => headers.push(h.innerText));
headers.sort();
console.table(headers);
```
