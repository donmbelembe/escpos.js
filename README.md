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

// [27,64,27,33,0,27,69,0,27,45,0,27,77,0,27,97,1,29,124,0,119,101,108,99,111,109,101,10,10,10,10,10,10,29,86,0]

```
