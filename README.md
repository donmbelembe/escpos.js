# escpos.js
escpos protocol, inspired by python-escpos and node-escpos

# demo

```javascript
var escpos = require('escpos.js');

function welcome () {

  var buffer = [];

  function _raw (buf) {
    buffer = buffer.concat(buf)
  }

  escpos(_raw)
  .hw()
  .set({align: 'center'})
  .text('welcome')
  .cut()
  ;

  return buffer;

};

console.log(welcome())
```
