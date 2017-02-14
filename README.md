# Livescript 2.0
---------------

![Logo](https://content.screencast.com/users/a.stegno/folders/Jing/media/31c82430-fe2d-4f78-8d13-93388950bccc/00000143.png)

## List of Requested Features:

### Livescript + Pug/Jade Internal Syntax Support (React Support)

```Livescript

{ render } = require \react-dom
{ create-class, inject-onload} = require \lsx
request = require \superagent
main = create-class do
    text: "Click Button"
    test-func: ->
        t = @
        err, data <-! request.get(\//root.flyber.net/test).end
        t.text = data.text
        t.force-update!
    render : ->
        ul.some-class
           li.another-div(on-click = @test-func title="Nested Div") @text
           li.another-div(on-click = @test-func title="Nested Div") Another Li
           

inject-onload main, \app

```

### Typescript Interfaces Support

```Livescript

interface Missing = Null | Undefined

interface User = 
  first-name: String
  last-name: String
  email: String | Missing
  
func = (user of User)->
   console.log user.first-name

wrong-model =
  something: "Another"

func wrong-model  #=> Compile Error

```

### Livescript to AST / AST to Livescript conversion without loosing of information 

```Livescript 

#LiveScript 1 looses curried function information in AST
carried-function = (x, xs)--> 


```


### Better Javascript Rendering 

``` Livescript

$scope
  ..prop = []
  ..prop2 = 2
```

Should be generated into 

``` Javscript
  $scope.prop = []

  $scope.prop2 = 2
```

instead of 

``` Javascript
  // looks ugly, unlogical, with extra reference and people don't like it
  var x$ = undefined
  x$ = $scope
  x$.prop = []
  x$.prop2 = 2
```





## Status
```
Descussions before Development 
```
Please propose your features in `Issues` section
