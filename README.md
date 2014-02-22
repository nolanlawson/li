Parse and format [Link header according to RFC 5988](http://www.w3.org/Protocols/9707-link-header.html).

## Install

    $ npm install li

Alsow works with bower, component.js, browserify, amd, etc.

## Usage

Parse a Link header:

~~~javascript
var li = require('li');
var someLinksHeader = '</api/users?page=0&per_page=2>; rel="first", ' +
                      '</api/users?page=1&per_page=2>; rel="next", ' +
                      '</api/users?page=3&per_page=2>; rel="last"';

console.log(li.parse(someLinksHeader));

// This will print:
// {
//   first: '/api/users?page=0&per_page=2',
//   next: '/api/users?page=1&per_page=2',
//   last: '/api/users?page=3&per_page=2'
// }
~~~

Generate a Link header as follow with stringify:

~~~javascript
var linksObject = {
  first : '/api/users?page=0&per_page=2',
  next  : '/api/users?page=1&per_page=2',
  last  : '/api/users?page=3&per_page=2',
};

console.log(parseLink.stringify(linksObject);

// This will print the string:
// </api/users?page=0&per_page=2>; rel="first",
// </api/users?page=1&per_page=2>; rel="next",
// </api/users?page=3&per_page=2>; rel="last"
~~~

## Development

    $ npm install -d

### Testing

    $ npm test

## License

MIT!
