# Rust Code Organization and Namespacing

Rust provides a robust module system to help organize code and avoid naming conflicts. Below are the key aspects of Rust's code organization and namespacing:

## 1. Modules (`mod`)
- **Used for organizing code into logical units.**
- **Declared with `mod module_name;`.**
- **Can be split into separate files.**

### Example:
```rust
mod math {
    pub fn add(a: i32, b: i32) -> i32 {
        a + b
    }
}

fn main() {
    let result = math::add(2, 3);
    println!("Result: {}", result);
}
```

## 2. Importing with `use`
- **Brings modules or functions into scope for easier access.**

### Example:
```rust
mod math {
    pub fn add(a: i32, b: i32) -> i32 {
        a + b
    }
}

use math::add;

fn main() {
    let result = add(5, 10);
    println!("Result: {}", result);
}
```

## 3. File and Directory Structure
- **Modules can be placed in separate files.**
- **File names match module names.**

### Example:
#### Project Structure:
```
src/
│── main.rs
│── math.rs
```

#### `math.rs`
```rust
pub fn add(a: i32, b: i32) -> i32 {
    a + b
}
```

#### `main.rs`
```rust
mod math;

fn main() {
    let result = math::add(3, 7);
    println!("Result: {}", result);
}
```

## 4. `super` and `crate` Keywords
- **`super`** → Access parent module.
- **`crate`** → Access the crate root.

### Example:
```rust
mod parent {
    pub mod child {
        pub fn hello() {
            println!("Hello, Rust!");
        }
    }
    pub fn call_child() {
        super::parent::child::hello();
    }
}

fn main() {
    parent::call_child();
}
```

## 5. Re-exporting with `pub use`
- **Simplifies external access to functions or modules.**

### Example:
```rust
mod math {
    pub fn add(a: i32, b: i32) -> i32 {
        a + b
    }
}

pub use math::add;

fn main() {
    let result = add(2, 2);
    println!("Result: {}", result);
}
```

## 6. `self`, `super`, and `crate` Navigation
- **`self`** → Access current module.
- **`super`** → Access parent module.
- **`crate`** → Access the root of the crate.

### Example:
```rust
mod parent {
    pub mod child {
        pub fn hello() {
            println!("Hello, Rust!");
        }
    }

    pub fn call_child() {
        self::child::hello();
    }
}

fn main() {
    parent::call_child();
}
```

## 7. External Crates with `Cargo.toml`
- **Use `Cargo.toml` to add dependencies.**

### Example (`Cargo.toml`):
```toml
[dependencies]
rand = "0.8"
```

### Example (`main.rs`):
```rust
use rand::Rng;

fn main() {
    let mut rng = rand::thread_rng();
    let number: i32 = rng.gen_range(1..101);
    println!("Random number: {}", number);
}
```



### Key Concepts:
- **`mod`** → Define a module.
- **`use`** → Import a module or function.
- **`pub`** → Make elements public.
- **File Structure** → Split modules into files.
- **`super`, `self`, `crate`** → Navigate modules.
- **`extern crate` & `Cargo.toml`** → Use external libraries.

With these concepts, Rust ensures well-structured, maintainable code! 🚀
