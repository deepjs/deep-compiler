# deep-compiler

javascript object/classes merging tools.

It merges recursively objects together AND modify the target.

# Example up

```javascript

var compiler = require("deep-compiler");

var src = {
	foo:true,
	bar:"hello world",
	zoo:[ 1, 2, 3 ],
	boom:{
		x:12
	}
};

var target = {
	foo:false,
	zoo:[ 4, 5 ],
	boom:{
		y:"yeah"
	}
};

compiler.up(target, src);

console.log(target);
```
Console output : 
```json
{
	"foo":true,
	"zoo":[ 4, 5, 1, 2, 3 ],
	"boom":{
		"y":"yeah",
		"x":12
	},
	"bar":"hello world"
}
```


# Example bottom

```javascript

var compiler = require("deep-compiler");


var src = {
	foo:true,
	bar:"hello world",
	zoo:[ 1, 2, 3 ],
	boom:{
		x:12
	}
};

var target = {
	foo:false,
	zoo:[ 4, 5 ],
	boom:{
		y:"yeah"
	}
};

compiler.bottom(src, target);

console.log(target);
```
Console output : 
```json
{
	"foo":false,
	"bar":"hello world",
	"zoo":[ 1, 2, 3, 4, 5 ],
	"boom":{
		"x":12,
		"y":"yeah"
	}
}
```


## Licence

The [MIT](http://opensource.org/licenses/MIT) License

Copyright (c) 2015 Gilles Coomans <gilles.coomans@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
