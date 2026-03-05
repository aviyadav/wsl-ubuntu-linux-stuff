#### shorten path

```
function prompt { "$(Split-Path -Leaf (Get-Location))> " }

or

function prompt {'PS ' + $(Get-Location | Split-Path -Leaf) + ">"}
```


> set env variables

```
$env:JAVA_HOME = "C:\Users\abcd\sw\jdk-25.0.2"
```
