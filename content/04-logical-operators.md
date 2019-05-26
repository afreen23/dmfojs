# Logical operators

## 1. What is the double negation?

> Example:
```js
!!true;        // true
!!false;       // false
!!(new Boolean(true));     // true
!!(new Boolean(false));     /
```

TODO: explanation

## 2. Why && and || do not return a boolean value like other languages ?

> Example:
```js
true && "Hello world" && 2   // 2
54.3 && false && 3           // false
"" && 1                      // ""
2 && "hi" && null            // null
```

```js
true || "Hello world" || 2   // true
false || 3 || 54.3           // 3
"" || 1                      // 1
"" || undefined || null      // 2
```

### Explanation

JavaScript coerces the operand value to boolean value to determine the value of a logical operation. If a value can be converted to true, the value is so-called truthy. If a value can be converted to false, the value is so-called falsy.

The logical operator && is evaluated from left to right and the evaluation stops once it finds a falsy value and returns the operand that has falsy value. If no falsy value is present then the last operand is returned.
> In example 1, all values are truthy hence last operand _2_ is returned
> In example 2, first value is truthy but as soon as second operand is evaluated it returned falsy value, hence _false_ is returned
> In example 3, "" is falsy hence evaluation stopped and next operand is not evaluated and _""_ returned
> In example 4, the first two operands are truthy but the last one is falsy hence _null_ returned

The logical operator || is the reverse of &&.

The logical operator || is evaluated from left to right and the evaluation stops once it finds a truthy value and returns the operand that has truthy value. If no truthy value is present then the last operand is returned.
> In example 1, the first operand has truthy value hence further operands are not evaluated and _true_ is returned
> In example 2, first value is falsy but as soon as second operand is evaluated it returned truthy value, hence _3_ is returned
> In example 3, "" is falsy hence evaluation moved forward  and _1_ returned
> In example 4, all the operands are false hence _null_ is returned


