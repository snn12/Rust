# Memory Safety in Rust

Memory safety is a fundamental concept in programming that ensures a program avoids common issues like:

- Null pointer dereferencing
- Buffer overflows
- Use-after-free errors
- Data races

## Ownership Rules

- Each value in Rust has a single owner.
- When the owner goes out of scope, the value is automatically dropped (freed).
- Ownership can be transferred (moved), but only one owner can exist at a time.

## Borrowing and References

- Rust allows borrowing references to data without transferring ownership.
- It enforces strict rules:
  - Either one mutable reference or multiple immutable references, but not both simultaneously.
- This prevents data races.

## Compile-Time Checks

- Rust’s compiler analyzes code at compile time to ensure memory safety rules are followed.
- If not, it throws an error, preventing unsafe code from running.
- This approach eliminates the need for a garbage collector while ensuring memory safety, making Rust both safe and efficient.

---

# Zero-Cost Abstractions (ZCA)

Zero-Cost Abstractions are a key feature of Rust, allowing developers to write high-level, expressive code without sacrificing performance.

## Generics

- Rust’s generics are monomorphized at compile time.
- The compiler generates specialized code for each type used, eliminating runtime type-checking overhead.

## Iterators

- Rust’s iterators are optimized to produce the same efficient machine code as manual loops.

## Traits

- Traits provide polymorphism without the runtime cost of virtual tables (vtables) unless explicitly needed (via dynamic dispatch).
