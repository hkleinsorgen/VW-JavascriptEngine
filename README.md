# VW-JavascriptEngine
Parser and runtime for ECMAScript aka Javascript.

The parser uses PetitParser. Requires a tweaked version which can be downloaded here:

https://github.com/hkleinsorgen/VW-PetitParser

The VisualWorks version uses the OrderedDictionary class from the `PDF` package from Cincoms Public Repository. See the class comment.

Parser example:
```
JSE.JSEParser new 
    factory: JSE.JSESyntaxTreeFactory new;
    parse: 'function hello() { return "Hello" }'
```

Runtime example:
```
| ast code |
ast := JSE.JSEParser new 
    factory: JSE.JSESyntaxTreeFactory new;
    parse: '42'.
code := JSE.JSERuntimeBuilderVisitor new visit: ast.
code run.
```
