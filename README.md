# Destructuring Quiz


```javascript
const circle = {
  radius: 10,
  color: 'orange',
  getArea: function() {
    return Math.PI * this.radius * this.radius;
  },
  getCircumference: function() {
    return 2 * Math.PI * this.radius;
  }
};

let {radius, getArea, getCircumference} = circle;


```
// getArea = new var contains function ```javascript return return Math.PI * this.radius * this.radius; ``` 
// [This  will refer to a window object or a global window object that does not have a radius property = undfined

```javascript
var x = this;
console.log(x);
> [object Window
```

How to solve it?

* We can refer to the undeclared variable in the destruction proecess

```javascript
const circle = {
  radius: 10,
  color: 'orange',
  lol: function() {
    return Math.PI * this.radius * this.radius;
  },
  getArea: function() {
    return circle.lol();
  },
  getCircumference: function() {
    return 2 * Math.PI * circle.radius;
  }
};

let {radius, getArea, getCircumference} = circle;

alert(getArea());

```

*  use the object's name in the function that has the radius property

```javascript
const circle = {
  radius: 10,
  color: 'orange',
  getArea: function() {
    return Math.PI * circle.radius * circle.radius;
  },
  getCircumference: function() {
    return 2 * Math.PI * circle.radius;
  }
};

let {radius, getArea, getCircumference} = circle;

alert(getArea());

```

*   

```javascript
const circle = {
  radius: 10,
  color: 'orange',
  getArea: function() {
    return Math.PI * this.radius * this.radius;
  },
  getCircumference: function() {
    return 2 * Math.PI * circle.radius;
  }
};

let {radius, getArea, getCircumference} = circle;

alert(circle.getArea());
```
