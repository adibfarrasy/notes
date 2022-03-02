## When to use receiver functions in go?

1. Functions with receiver is a METHOD. Methods in OOP languages is associated with objects of a class.
   In Go it can be used with structs.
2. Normal FUNCTION works with data. It is preferable to be used when high reusability processing non-object data is needed.

general rule: is the operation done BY the object/ struct or TO the object/ struct?
if done BY the object it should be method/ functions with receivers, e.g. duck.quack()
if done TO the object it should be member function (can be by Interface), e.g. kill(duck)
if neither (argument is not type struct), it should be a function. e.g. sum(...int)
