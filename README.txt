Pass a function to def.
Internal name is taken from that name, and it's suggested to use one.
Argument typing and optionalness is taken from the argument name:
1) name //no type checking, required
2) Type_name //type checking (Type is a class like String or Number), required
3) name$ //no type checking, optional
4) Type_name$ //type checking, optional

How to use:
var def = require("def.js").def; //If using from Node.JS
var myFunc = def(function myFunc(prefix,Number_body$,String_suffix$){
	// Defaults:
	body = this.body || 1;
	suffix = this.suffix || "";
	
	return "" + (prefix + body) + suffix;
});

Example executions and results:
> myFunc(":)");
':)1'
> myFunc(12);
'13'
> myFunc(3,"abc");
Function "myFunc" argument 1 must be of type Number
> myFunc(3,1,"abc");
'4abc'
> myFunc("a",1,"abc");
'a1abc'
