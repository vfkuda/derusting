## Project goal
1. Refactor some legacy code. 
2. Keep it working, 
3. Make it better.

## Tasks

[original code commit](https://github.com/vfkuda/derusting/commit/1b7d9e5dafa4c769bc29c35959db9e45dd085299)

The following code issues / bad practices need to be fixed:

[ ] Using unnecessary clone() calls instead of references.
[x] Using Rc<RefCell<T>> where references would be sufficient.
[ ] Using loops instead of iterators.
[ ] Using unsafe unnecessarily.
[ ] Having a singleton that can be avoided.
[ ] Using excessive validation instead of tight types.
[ ] Duplicating code for parameters of different types instead of using generics.
[ ] Using trait objects in places where generics would be sufficient.
[ ] Using a sequence of if statements instead of a single match.
[ ] Having an enum where one of the variants occupies several kilobytes of stack space.
[ ] Using panics instead of returning errors.

[!HINT]
Tests shall keep passing after refactoring: 

Test comands:
```
cargo test -- --nocapture
```
```
cargo test test_all -- --nocapture
```
```
cargo run example.log 
```
