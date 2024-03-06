# Math expression challenge

Parse mathematical expressions given in a prefix notation, and provide an API to evaluate the parsed expression with variable substitution.

Expected mathematical operations are:
- `+`, `-`, `*` and `/`, which take 2 operands.
- `max` and `min`, which take 1..N operands.

Operands will be in the form of **integer** values, **variable** name or **sub-expressions** surrounded by parenthesis.

If an ASCII string is provided as an input operand it should be treated as a variable.

Each token will be separated by whitespace.

Valid syntax:
```
Expression                  | Eval input variables | Eval result
( + 5 6 )                   | {}                   | 11
( - 10 2 )                  | {}                   | 8
( * ( + 1 2 ) ( - 3 1 ) )   | {}                   | 6
( + 2 x )                   | {x: 10}              | 12
5                           | {}                   | 5
x                           | {x: 10}              | 10
( max 1 )                   | {}                   | 1
( max 1 20 x y )            | {x: 5, y: 7}         | 20
( min 1 2 3 )               | {}                   | 1
```

Provide an API to parse an expression, and another API to evaluate the parsed expression given substituted variables.

Example APIs:
```
Object parse(String expression); // feel free to replace Object with your own type
int evaluate(Object parsedExpression, Map<String, Integer> variableMap);
```
