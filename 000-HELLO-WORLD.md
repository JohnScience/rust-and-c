| C | Rust | Comparison |
|---|---|---|
| #include <stdio.h> | use std::io::*; | Unlike in C, importing items in Rust is done with a statement instead of a macro. It is better for the compile times, is fool-proof from linking errors, and is more ergonomic for writing software components because there's no need to add include guards. In addition, in Rust you can explicitly name the items that you want to import, which makes the code much easier to read. |
| // How do you do single-line comments?  | // Just like you! | Single-line comments in Rust and C are identical |
| /* What about multi-line comments?    Are they identical too? */ | /* Yes!    Absolutely! */ | Multi-line comments in Rust and C are identical as well. |
| int main() {   return 0; } | fn main() { } | Just like in C, the default entry to the program is main() function. However, in Rust the most basic main function returns a value of a type that represents nothing, an instance of () ["unit"] type, which is the Rust's equivalent of void in C. |
| printf("Hello world"); | print!("Hello world"); | Just like in C, statements in Rust are delimited with semicolons (";"). However, Rust programmers traditionally use macros instead of functions when dealing with variadic arguments. At the moment of writing, C-style variadic functions in Rust are supported only for compatibility with C. |
| print("Hello world\n"); | print!("Hello world\n"); | Just like in C, string literals in Rust can contain a "\n" escaped sequence that corresponds to a new line. |

## Side by side of hello world programs

![hello world programs](https://i.imgur.com/w9lXVGh.png)

Note that in the Rust counterpart there is no single [`use` declaration](https://doc.rust-lang.org/reference/items/use-declarations.html), which are usually responsible for importing items. In Rust, most popular items from a standard library are re-exported to [`std::prelude`](https://doc.rust-lang.org/std/prelude/index.html), which is then implicitly imported into every module by default.
