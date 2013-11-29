
# Synopsis

Concise creation of delegate methods for your classes/objects

[![NPM](https://nodei.co/npm/delega.png?downloads=true)](https://nodei.co/npm/delega/)

[![Build Status](https://travis-ci.org/mariocasciaro/delega.png)](https://travis-ci.org/mariocasciaro/delega)
[![Coverage Status](https://coveralls.io/repos/mariocasciaro/delega/badge.png)](https://coveralls.io/r/mariocasciaro/delega)

[![browser support](https://ci.testling.com/mariocasciaro/delega.png)](https://ci.testling.com/mariocasciaro/delega)

## Usage
__For objects__
```javascript
var objA = {
  foo: function() {
    return "a";
  },
  foo2:  function() {
    return "b";
  }
};

var objB = {};
delega.delegateToObject(objB, objA, ['foo','foo2']);

expect(objB.foo()).to.be.equal("a");
expect(objB.foo2()).to.be.equal("b");
```

__For classes__
```javascript
var objA = {
  foo: function() {
    return "a";
  },
  foo2: function() {
    return "b";
  }
};

var clazzB = function() {
  this.a = objA;
};

delega.delegateToProperty(objB, 'a', ['foo', 'foo2']);

expect(new clazzB().foo()).to.be.equal("a");
expect(new clazzB().foo2()).to.be.equal("b");
```

-----
[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/mariocasciaro/delega/trend.png)](https://bitdeli.com/free "Bitdeli Badge")