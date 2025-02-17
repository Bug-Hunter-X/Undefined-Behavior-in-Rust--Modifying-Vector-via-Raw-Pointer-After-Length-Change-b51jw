# Rust Undefined Behavior Example

This repository demonstrates a common source of undefined behavior in Rust: modifying a vector through a raw pointer after its length or capacity has changed.  The `bug.rs` file contains the buggy code, while `bugSolution.rs` provides a safe and correct alternative.

**Bug:** The original code uses `as_mut_ptr()` to obtain a raw pointer to the vector's data.  Subsequently modifying the data via this pointer after vector operations (like appending or removing elements) that potentially change the vector's memory layout leads to undefined behavior.  The program might crash, produce incorrect results, or seemingly work correctly until encountering a specific input.

**Solution:**  The solution avoids the unsafe approach and leverages Rust's safe abstractions to ensure memory safety and predictable behavior.