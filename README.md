# React &lt;Frame /> component

[![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][depstat-image]][depstat-url]

This component allows you to encapsulate your entire React application or per component in an iFrame.

```bash
npm install --save react-frame-component
```

## How to use:

```js
var Frame = require('react-frame-component');
```

Go check out the [demo] [demo-url].

```html
var Header = React.createClass({
  render: function() {
    return (
      <Frame>
        <h1>{this.props.children}</h1>
      </Frame>
    );
  }
});

React.render(<Header>Hello</Header>, document.body);
```

Or you can wrap it at the `render` call.

```html
React.render(
  <Frame>
    <Header>Hello</Header>
  </Frame>,
  document.body
);
```

#####Props:

######head
`head:  React.PropTypes.node`

The `head` prop is a dom node that gets inserted before the children of the frame. Note that this is injected into the body of frame (see the blog post for why). This has the benefit of being able to update and works for stylesheets.

######initialContent
`initialContent:  React.PropTypes.string`

Defaults to `'<html><head></head><body><div></div></body></html>'`

The `initialContent` props is the initial html injected into frame. It is only injected once, but allows you to insert any html into the frame (e.g. a head tag, script tags, etc). Note that it does *not* update if you change the prop. Also at least one div is required in the body of the html, which we use to render the react dom into.

## More info

I wrote a [blog post] [blog-url] about building this component.

## License

Copyright 2014, Ryan Seddon.
This content is released under the MIT license http://ryanseddon.mit-license.org

[npm-url]: https://npmjs.org/package/react-frame-component
[npm-image]: https://badge.fury.io/js/react-frame-component.png

[travis-url]: http://travis-ci.org/ryanseddon/react-frame-component
[travis-image]: https://secure.travis-ci.org/ryanseddon/react-frame-component.png?branch=master

[depstat-url]: https://david-dm.org/ryanseddon/react-frame-component
[depstat-image]: https://david-dm.org/ryanseddon/react-frame-component.png

[demo-url]: http://ryanseddon.github.io/react-frame-component/
[blog-url]: http://developer.zendesk.com/blog/2014/05/13/rendering-to-iframes-in-react/
