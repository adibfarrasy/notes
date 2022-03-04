# When to Use What Test Doubles?

reference article: https://searchsoftwarequality.techtarget.com/tip/Inside-5-types-of-test-doubles

## 5 types of test doubles:

- test stubs
- mocks
- dummies
- spies
- fakes

### Stubs

provide hard coded values. substitute values.

### Mocks

provide pre-determined result whenever it is called. good for isolating tests from external dependencies by mocking the dependencies to return pre-defined results. substitute methods.

### Dummies

provide a valid parameter with no data when required by the system under test. substitute parameters.

### Spies

similar to stubs, but it also tracks how the system under test uses the value and how the values change.

### Fakes

simulates test objects with different implementations, such as in-memory database instead of actual database. it allows test to run faster and less prone to errors. substitutes bottlenecks in the system under tests.
