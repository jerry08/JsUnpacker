<h1 align="center">
    JsUnpacker
</h1>

<p align="center">
   <a href="https://nuget.org/packages/JsUnpacker"><img src="https://img.shields.io/nuget/dt/JsUnpacker.svg?label=Downloads&color=%233DDC84&logo=nuget&logoColor=%23fff&style=for-the-badge"></a>
</p>

**JsUnpacker** is a class to decode Dean Edwards' JavaScript Packer.

## Usage
``` c#
using JsUnpacker;

var script = "eval(function(p,a,c,k,e,r){e=String;if(!''.replace(/^/,String)){while(c--)r[c]=k[c]||c;k=[function(e){return r[e]}];e=function(){return'\\\\w+'};c=1};while(c--)if(k[c])p=p.replace(new RegExp('\\\\b'+e(c)+'\\\\b','g'),k[c]);return p}('2(0){1(\"3: \"+0);1(\"4\")}',5,5,'str|alert|function|message|ok'.split('|'),0,{}))";

if (Unpacker.IsPacked(script))
{
    var result = Unpacker.UnpackAndCombine(script);
    Console.WriteLine(result);
}
else
{
    Console.WriteLine("Not P.A.C.K.E.R. coded");
}
```

## Result
```
function(str){alert("message: "+str);alert("ok")}
```
