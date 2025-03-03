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
