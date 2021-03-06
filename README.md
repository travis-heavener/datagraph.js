# datagraph.js

a library that lets you see a physical demonstration of your data on a 2-dimensional graph

## demo

### download the DataGraph library for your project!

https://raw.githubusercontent.com/travis-heavener/datagraph.js/master/datagraph.1.1.js

### or embed the online version!

https://cdn.jsdelivr.net/gh/travis-heavener/datagraph.js/datagraph.1.1.js

to create the most basic DataGraph:

```
const data = [ [1, 2], [2, 3], [3, 4], [4, 5] ];
let graph = new DataGraph( data );
//opens a full-size graph in a new window
```

to create a graph with a width parameter of 500px and a height parameter of 600px:

```
let graph = new DataGraph( data, 500, 600 );
//a graph with dimensions 500px by 600px has appeared!
```

to add a trendline, pass any function that takes in input and gives output as the fourth parameter:

```
const trendline = (x) => {
  return x ** 2; //x squared
}

let graph = new DataGraph( data, null, null, trendline );
//a graph appears with a trendline! woohoo!
```

to specify the graph's x and y ranges:

```
let graph = new DataGraph( data, 600, 600, null, 12, 12 );
//a graph appears with a maximum/minimum x value of +/-6 and a maximum/minimum y value of +/-6! hooray!
```

#### **note:**

- any parameters can be left **null** to ignore their input (ex. you want to add a trendline but keep default width and height)
`let graph = new DataGraph( data, null, null, trendline );`

## documentation

in the DataGraph function, the following parameters can be modified:

- data
- window width
- window height
- trendline
- graph x range
- graph y range

### data

the data parameter represents the data that is to be displayed in the graph. ex:
```
let data = [
/*[x, y]*/
  [1, 2],
  [2, 3],
  [3, 4]
];

let graph = new DataGraph(data);
//shows the data in a visual graph
```

### window width & window height

the window width and height parameters represent the width and height of the created window, in pixels (px). ex:
```
let graph = new DataGraph(data, 600, 400);
//makes a graph with a width of 600px and a height of 400px
```

### trendline

a function that takes a number as input and returns a number as an output. ex:
```
let trendlineFunc = (x) => {
  return Math.pow(x, 2); //x squared (x^2) graph
}
let graph = new DataGraph(data, 600, 400, trendlineFunc);
//makes a graph with a trendline of the x^2 function
```

### graph x range & graph y range

the graph x range and y range each represent the maximum and minimum range of the x and y axes.
the maximum shown x and y values are half of the corresponding parameter ex:
```
let graph = new DataGraph(data, 600, 600, null, 10, 12);
//makes a graph with an x range of +/-5 and a y range of +/-6
```
