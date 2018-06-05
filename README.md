![Code Style: Really Bad](https://alan.liangcn.ml/CodeStyle.svg)

Code Style of [Alan-Liang](https://github.com/Alan-Liang)
===

## Variables
Always use `var`.
```javascript
//good
var foo;
var bar="baz";

//bad
const foo="bar";
let bar="baz";

//terrible
foo="bar";
```

## Strings
Always use double quotes.
```javascript
//good
var str="some \"string\"";
var str2="some\n"+
         "long\n"+
         "long\n"+
         "string";

//bad
var str='string';
var str2=`string is ${str}`;
var str3=`some
long
string
`;
```

## Functions
Always use normal function notion. Never use arrow functions or classes.
> **Why?**
> For backward compatibility.

```javascript
//good
function foo(bar){
	return bar;
};
var bar=function(baz){
	return baz;
};
baz(function(err,res){
	if(err)
		console.log(err.stack);
	else
		console.log(res);
});
function C(id){
	this.id=id;
};
C.prototype.setId=function(id){
	this.id=id;
	return this;
};
C.prototype.getId=function(){
	return this.id;
};

//bad
var foo=new Function("bar","return bar;");
var bar=baz=>baz;
baz((err,res)=>{
	//same as above
});
class C{
	constructor(id){
		this.id=id;
	}
	getId(){
		return this.id;
	}
	setId(id){
		this.id=id;
		return this;
	}
}
```

## Indents
Use tab when coding on cell phone, and 2 spaces on computer.

## Spaces
No space when unnecessary.
> **Why?**
> no why.

```javascript
//good
var foo=1;
function foo(a,b){}
var foo=function(a,b){};
if(foo>1){
	foo-=233;
}

//bad
var foo = 1;
function foo(a, b) {}
var foo = function (a, b) {};
if( foo > 1 ) {
	foo -= 233;
}
```

## Naming
Always camelCaseLikeThis.

## Modules
Always use CommonJS `require()`s.
```javascript
//good
var foo=require("./foo");
module.exports=foo.bar.baz;

//bad
import {bar} from foo;
export default bar.baz;
```

## Arrays
Always use `for`s.
```javascript
var _arr=[1,2,3,4,5,6,7,8,9,10];
var arr=[];

//good
for(var i=0;i<_arr.length>i++){
	arr.push(_arr[i]+1);
}

//bad
_arr.forEach(function(el){
	arr.push(el+1);
});
```

## Other
1. Use `;`.
2. Use things as **native** as possible. (e.g. Do not use jQuery unless it is required.)