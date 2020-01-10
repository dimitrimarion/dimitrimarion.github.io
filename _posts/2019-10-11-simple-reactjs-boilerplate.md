---
title: Simple React.js Boilerplate
---

I created a simple React.js boilerplate using Parcel. It's a simple starter kit that you can easily extend. Only "react" and "react-dom" are installed, you decide which router or state management library or any other libraries you want to use.

**Link to the boilerplate**: [Simple React.js Boilerplate](https://github.com/dimitrimarion/react-parcel-boilerplate)

<!--more-->

## Getting started

You can click on "Use this template" to create another repository or clone the repository:

`$ git clone https://github.com/dimitrimarion/react-parcel-boilerplate.git`

Run the setup:

`$ npm run setup`

Start the development server:

`$ npm run dev`

Bundle the application for production:

`$ npm run build`

## Useful packages

{:.styled-list}
* [babel-plugin-module-resolver](https://github.com/tleunen/babel-plugin-module-resolver): this plugin simplifies the import path in your project.

```javascript
// Use this:
import dog from "@images/dog.jpg";
// Instead of that:
import dog from "../../../images/dog.jpg"
```

You just need to add an alias in `.babelrc`:
```javascript
 [
   "module-resolver",
      {
        "root": ["./src"],
        "alias": {
          "@images": "./assets/images"
        }
      }
  ]
```

{:.styled-list}
* [@babel/plugin-proposal-class-properties](https://babeljs.io/docs/en/next/babel-plugin-proposal-class-properties.html): this plugin lets you use class properties.

Without class properties:
```javascript
class Button extends Component {
  constructor(props) {
    super(props);
    this.state = { clicked: false };
    this.handleClick = this.handleClick.bind(this);
  }
  
  handleClick() {
    this.setState({ clicked: true });
  }
  
  render() {
    return <button onClick={this.handleClick}>Click Me!</button>;
  }
}
```
With class properties and arrow function, there is no need to bind `this` and the code is shorter:
```javascript
class Button extends Component {
  state = { clicked: false };
  
  handleClick = () => this.setState({ clicked: true });
  
  render() {
    return <button onClick={this.handleClick}>Click Me!</button>;
  }
}
```

## Conclusion

This is a very simple boilerplate, it doesn't include advanced things like state management or unit testing but I think it's a good starting point for somebody
learning React.js.
