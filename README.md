# Implement d3 Margin Convention

## Install

`npm install d3-margin-convention`  

`bower install d3-margin-convention`  


## Usage

Call the d3-margin-convention function. 1)Use chained method to update `width`, `height`, or `margin` of the svg container, 2)Use `innerChart` to get the transformed <g> element. 3) Use `innerWidth` or `innerHeight` to get the actual chart size, such as translate the x axis.  

## Example

### Webpack

#### entry.js

```
var d3Chart = require('d3-margin-convention');

var chart = d3Chart().width(800).height(500);

var svg = d3.select("body").append("svg")
	.datum(data)
	.call(chart);

svg.innerChart.append("g")
	.attr("transform","translate(0,"+chart.innerHeight+")")
	.attr("class","axis x")
```


### Browser

#### index.html

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.5/d3.min.js"></script>
<script src="./index.js"></script>
<script>
window.onload = function(){
  var chart = marginConvention().margin({
		top:10,
		right:20,
		bottom:30,
		left:30
	});
  var svg = d3.select("body").append("svg")
  	.datum(data)
  	.call(chart);

  svg.innerChart.append("g")
  	.attr("transform","translate(0,"+chart.innerHeight+")")
  	.attr("class","axis x")
}
</script>
```
