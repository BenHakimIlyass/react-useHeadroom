## react-useHeadroom

[![TypeScript](https://badges.frapsoft.com/typescript/code/typescript.svg?v=101)](https://github.com/microsoft/TypeScript)

A fully-typed lightweight react custom hook that returns the state of the shown/hidden header (headroom).

Here is a demo [live](https://codesandbox.io/s/tender-snowflake-zf79v).

## Installation

### Typescript

`yarn add react-useheadroom@types`

### Javascript

`yarn add react-useheadroom` or `npm install react-useheadroom`

## Usage

```jsx
import * as React from 'react';
import './styles.css';
import useHeadroom from 'react-useheadroom';

const App = () => {
  const isPinned = useHeadroom({});
  return (
    <div
      className='header'
      style={{
        transform: isPinned
          ? `translate3d(0,0px,0)`
          : `translate3d(0,-100px,0)`,
      }}
    />
  );
};

export default App;
```

## Props

Optionnaly you can pass those props.

- **fixAt** the header will be fixed at this value, and cannot be unpinned (default value is 0).

- **onPin** callback

- **onUnpin** callback

- **onFix** callback

- **onUnfix** callback

**Example**

```jsx
import * as React from "react";
import "./styles.css";
import useHeadroom from "react-useheadroom";

const App = () => {
  const isPinned = useHeadroom({
    fixAt:  /* e.g: 400 */,
    onPin: () => /* do something here ... */,
    onUnpin: () => /* do something here ... */,
    onFix: (fixedAt) => /* do something here ... */,
    onUnFix: (fixedAt) => /* do something here ... */
  });
  return (
    <div
      className="header"
      style={{
        transform: isPinned
          ? `translate3d(0,0px,0)`
          : `translate3d(0,-100px,0)`
      }}
    />
  );
}

export default App;
```
