---
title: "React boilerplates"
date: 2019-10-10
draft: false
categories:
  - React

description: quick boilerplates and templates
tags:
  - react
  - boilerplate
---

## Komponenty State i Stateless

Parent przekazuje stan do Child i renderuje Child.
Child renderuje stan otrzymany z Parent

### Parent

```
# react component
import React from 'react'
import ReactDOM from 'react-dom'
import {Child} from './Child'


class Parent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { name: 'Value' };
  }

  render() {
    return <Child name={this.state.name} />;
  }
}

ReactDOM.render(
  <Parent />,
  document.getElementById('app')
)
```

### Child

```
import React from 'react';

export class Child extends React.Component {
  render() {
    return <h1>Hey, my name is {this.props.name}!</h1>;
  }
};
```
