## Project goal
1. Refactor some legacy code. 
2. Keep it working, 
3. Make it better.

## Tasks

[original code commit](https://github.com/vfkuda/derusting/commit/1b7d9e5dafa4c769bc29c35959db9e45dd085299)

The following code issues / bad practices needed to be fixed:
* [x] Using unnecessary clone() calls instead of references.
* [x] Using Rc<RefCell<T>> where references would be sufficient.
* [x] Using unsafe unnecessarily.
* [x] Having a singleton that can be avoided.
> [!NOTE] 
> I would rather prefer to keep once assembled object as a singleton. But I change the interface
* [x] Using excessive validation instead of tight types.
* [x] Duplicating code for parameters of different types instead of using generics.
* [x] Using trait objects in places where generics would be sufficient.
* [x] Having an enum where one of the variants occupies several kilobytes of stack space.

Following issues were probably gone by previous refactoring: 
* [?] Using loops instead of iterators.
* [?] Using a sequence of if statements instead of a single match.
* [?] Using panics instead of returning errors.

> [!IMPORTANT]
> Tests shall keep passing after refactoring: 

Test commands:
```
cargo test -- --nocapture
```
```
cargo test test_all -- --nocapture
```
```
cargo run example.log 
```
* the bestest
```
cargo nextest run 
```
