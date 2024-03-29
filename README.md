# traverse-all 👌

<p>
  <img src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://github.com/DZG-MELODY/traverse#readme">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" target="_blank" />
  </a>
  <a href="https://github.com/DZG-MELODY/traverse/graphs/commit-activity">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" target="_blank" />
  </a>
  <a href="https://github.com/DZG-MELODY/traverse/blob/master/LICENSE">
    <img alt="License: ISC" src="https://img.shields.io/badge/License-ISC-yellow.svg" target="_blank" />
  </a>
</p>

> methods to traverse every thing!

more language:

[zh-CN](./README-zh-CN.md)

## Install

```sh
npm install traverse-all
```

## Usage

### base usage

#### import module

```js
const Traverse = require("traverse-all");

Traverse.traverse_recursive(nodes, options);
```

#### import defined method from module

```js
const { traverse_recursive } = require("traverse-all");

traverse_recursive(nodes, options);
```

## Methods Usage

### traverse_recursive(nodes,options)

- **nodes**：`Array` root nodes
- **options**：`Object` traverse options which includes:
  - predicate：`Function` **required**
  - nodeHandle：`Function` **required**
  - exclude: `Function`
  - ignore: `Function`
- **return** `Promise<any>`

predicate(node):{done:`Boolean`,iterators:`Array`}

- node：current node
- done：whether current node finish traversing
- iterators：node array to traverse of current node

nodeHandle(node,params,options,result):node

- node：current node
- params：node traverse params
- options：traverse options
- result：result which can be trans to next node
- return：node **NOTE**：even do nothing,you must return the node，ex：`node=>node`

**params**：

- path：`Array<node>`node path
- isLeaf：`Boolean`
- isFirst：`Boolean`is first node of current traverse level
- isLast：`Boolean`is last node of current traverse level

## Author

👤 **dzg**

- Github: [@DZG-MELODY](https://github.com/DZG-MELODY)

## Show your support

Give a ⭐️ if this project helped you!

## 📝 License

Copyright © 2019 [dzg](https://github.com/DZG-MELODY).

This project is [ISC](https://github.com/DZG-MELODY/traverse/blob/master/LICENSE) licensed.
