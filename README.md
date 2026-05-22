## Project goal
1. Refactor some legacy code. 
2. Keep it working, 
3. Make it better.

## Tasks

[original code commit](https://github.com/vfkuda/derusting/commit/1b7d9e5dafa4c769bc29c35959db9e45dd085299)

The following code issues / bad practices need to be fixed:

1. Using unnecessary clone() calls instead of references.
1. Using Rc<RefCell<T>> where references would be sufficient.
1. Using loops instead of iterators.
1. Using unsafe unnecessarily.
1. Having a singleton that can be avoided.
1. Using excessive validation instead of tight types.
1. Duplicating code for parameters of different types instead of using generics.
1. Using trait objects in places where generics would be sufficient.
1. Using a sequence of if statements instead of a single match.
1. Having an enum where one of the variants occupies several kilobytes of stack space.
1. Using panics instead of returning errors.

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
