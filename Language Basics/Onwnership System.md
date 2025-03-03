# Rust Concepts: Ownership, Memory Safety, Borrowing, References, Slices, and Stack vs Heap

Rust is a systems programming language that emphasizes memory safety and performance. It achieves this through its unique ownership system, borrowing, and strict compile-time checks. Below, we’ll dive into key Rust concepts like ownership, memory safety, borrowing, references, slices, and the differences between stack and heap.

---

## 1. Ownership System

The ownership system is one of Rust's most important features, ensuring memory safety by managing how data is accessed and when it is deallocated. In Rust, every value has a single owner, and the owner is responsible for managing the value's lifetime.

### Ownership Rules:
1. **Single Owner**: Each value has only one owner at a time.
2. **Move Semantics**: When a value is assigned to another variable, ownership is transferred (moved). For example:
   ```rust
   let s1 = String::from("hello");
   let s2 = s1; // Ownership of s1 is moved to s2.
   // println!("{}", s1); // Error! s1 is no longer valid.

## 2. Memory Safety

Rust ensures memory safety through its ownership system and borrowing mechanism. This prevents common memory errors such as:

- **Double Free**: Attempting to free the same memory twice.
- **Null Pointers**: Dereferencing a null or invalid pointer.
- **Data Races**: Concurrent access to the same data without proper synchronization.

---

## 3. Borrowing, References, and Slices

### Borrowing:
Borrowing allows you to use a value without taking ownership. This is done using references.

#### Immutable and Mutable References:
```rust
let s1 = String::from("hello");
let len = calculate_length(&s1); // Immutable reference
println!("Length of '{}': {}", s1, len);

fn calculate_length(s: &String) -> usize {
    s.len()
}

let mut s2 = String::from("world");
change(&mut s2); // Mutable reference
println!("{}", s2);

fn change(s: &mut String) {
    s.push_str("!");
}

# Deep Dive: Stack vs Heap

## Stack
The stack is a fast, automatically managed memory region.

- Variables are stored in a Last-In-First-Out (LIFO) order.
- Ideal for fixed-size data with a known lifetime.
- Example: Primitive types (integers, floats, booleans) and fixed-size structs are stored on the stack.

## Heap
The heap is a dynamic memory region that can grow or shrink.

- Data on the heap is accessed via pointers.
- Example: Types like `Box`, `Vec`, and `String` are stored on the heap.

### Example Code
```rust
let s = String::from("hello"); // String is stored on the heap.
let x = 5; // x is stored on the stack.
```

## 4. Stack vs Heap Comparison

| Stack | Heap |
|-------|------|
| Fast, automatic management | Flexible, dynamic memory |
| Fixed-size data | Variable-size data |
| No pointers needed | Accessed via pointers |
