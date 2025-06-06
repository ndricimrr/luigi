<!-- meta
{
  "node": {
    "label": "Luigi Element API",
    "category": {
      "label": "API Reference",
      "collapsible": true
    },
    "metaData": {
      "categoryPosition": 7,
      "position": 4
    }
  }
}
meta -->

# Luigi Element

The `LuigiElement` class is a base class for building web component micro frontends within the Luigi framework. It provides essential functionality for rendering and managing the lifecycle of web components.

## Example Usage

To create a custom web component, extend `LuigiElement` and implement the required methods such as `render()`, `afterInit()`, and `onContextUpdate()`.

```js
class MyComponent extends LuigiElement {
  render(ctx) {
    return `<div>Hello, ${ctx.user.name}!</div>`;
  }

  afterInit(ctx) {
    console.log('MyComponent initialized with context:', ctx);
  }

  onContextUpdate(ctx) {
    console.log('Context updated:', ctx);
  }
}
```

The html function allows for creating HTML templates with interpolated values.

```js
const name = 'World';
const template = html`<p>Hello, ${name}!</p>`;
console.log(template); // Output: <p>Hello, World!</p>
```

## API Reference

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### LuigiElement

**Extends HTMLElement**

Base class for Luigi web component micro frontends.

#### Parameters

*   `options`  

#### afterInit

Override to execute logic after initialization of the web component, i.e.
after internal rendering and all context data set.

##### Parameters

*   `ctx` **any** The context object passed by luigi core

#### render

Override to return the html template string defining the web component view.

##### Parameters

*   `ctx` **any** The context object passed by luigi core

#### update

Override to execute logic after an attribute of this web component has changed.

#### onContextUpdate

Override to execute logic when a new context object is set.

##### Parameters

*   `ctx` **any** The new context object passed by luigi core

#### querySelector

*   **See**: ParentNode.querySelector

Query selector operating on shadow root.

##### Parameters

*   `selector`  

### html

Html string processing according to luigi functionality.
Also useful in combination with LitElement VS Code plugins.

#### Parameters

*   `literal` **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The literal to process.
*   `keys` **...any** 

Returns **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Returns the processed literal.
