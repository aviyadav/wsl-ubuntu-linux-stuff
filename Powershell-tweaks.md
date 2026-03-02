#### shorten path

```
function prompt { "$(Split-Path -Leaf (Get-Location))> " }

or

function prompt {'PS ' + $(Get-Location | Split-Path -Leaf) + ">"}
```
