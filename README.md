# curried-functions
Quick example of a library object for curried functions



```var curry = {
  // 1. 'Heidi' is passed in as name. 
  // 2. greetDeeplyCurried is called and name passed on via 'this'.
  // Note that we can't use fat arrow functions here as 'this' points to a different target.
  
  awkwardCurry: function (name) {
    this.greetDeeplyCurried('This')('...')('?')(name)
  },
  helloCurry: function (name) {
    this.greetDeeplyCurried('Hello')(', ')('.')(name)
  },
  harrisonCurry: function (name) {
    this.greetDeeplyCurried('Hello')(', is that ')(' on your shirt... psyche')(name)
  },

  greetDeeplyCurried: function (greeting) {
    // var greeting = this.init.arguments[arguments.length - 1]
    return function (separator) {
      return function (emphasis) {
        return function (name) {
          console.log(greeting + separator + name + emphasis);
          // console.log('greeting: ' + greeting + ', separator: ' + separator + ', name: ' + name + ', emphasis: ' + emphasis)
        }
      }
    }
  }
};

// Pass in name.
curry.helloCurry('Vindaloo');
curry.awkwardCurry('Vindaloo');
curry.harrisonCurry('Vindaloo');```

