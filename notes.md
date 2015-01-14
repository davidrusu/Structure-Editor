# Notes
Antlr looks like an ideal parser generator.
It would allow us to build an ast as the user is typing and hopefully be able to tell us what the next valid characters could be
What we need is a state machine defined by a grammar. That way as the user types we can know what is expected next
```
fn x = 2 + x * 2

Typed : What's Visible
''    : {|}
'f'   : {f| _ = _}
'n'   : {fn| _ = _}
' '   : {fn {|} = _}
'x'   : {fn {x|} _ = _}
' '   : {fn {x} {|} = _}
' '   : {fn {x} = {|}}
'2'   : {fn {x} = {2|}}
' '   : {fn {x} = {2} |}
'+'   : {fn {x} = {{2} +| _}}
' '   : {fn {x} = {{2} + {|}}}
'x'   : {fn {x} = {{2} + {x|}}}
' '   : {fn {x} = {{2} + {x} |}}
'*'   : {fn {x} = {{2} + {{x} *| _}}
' '   : {fn {x} = {{2} + {{x} * {|}}}
'2'   : {fn {x} = {{2} + {{x} * {2|}}}
'\n'  : {fn {x} = {{2} + {{x} * {2}}}
```

## Existing Work
- Subtext
- SEdit
- interlisp
- [Some concept work done by chris done](https://www.youtube.com/watch?v=v2ypDcUM06U)

## Grammers
- could use texmate grammers as nearly every language has one
- Peggy
- Antlr

## Parsing Grammers
- Parsing Peggy is a given

## Type Checking
- 


##Phases
