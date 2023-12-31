# Comparison of "Sheeps" programs

| C | Rust | Comparison |
|---|---|---|
| int sheepCount; | let mut sheep_count; | Variable declarations/definitions in C and Rust are slightly different. In C, variables are mutable by default, while in Rust they are immutable. Immutability by default allows the compilers to perform optimizations better. In addition, in C variable definitions/declarations start with a type name, while in Rust the type name doesn't even need to be specified and nearly always can be inferred by the compiler. In Rust, the default type is i32 (signed 32-bit integer). Regarding explicit type choices, Rust's conventions favor unsigned integers where possible, unlike in C, where they're typically discouraged unless there's a need for wrapping arithmetic. Also, in Rust the use of precisely-sized types is considerably more prominent. The naming conventions for variables in Rust suggest snake_case, while in C naming conventions for variables suggest camelCase. |
| sheepCount = 0; | sheep_count = 0; | Initialization (the first assignment with some value) of a variable with some constant value is identical |
| sheepCount = sheepCount + 2 * 2; | sheep_count = sheep_count + 2 * 2; | Assignment of an expression to a variable is identical as well. |
| printf("There are %d sheeps in the pen.\n", sheepCount); | print!("There are {} sheeps int the pen.\n", sheep_count); | In Rust, printing values doesn't require format specifiers (like "%d"). Instead, "{}" placeholders are used. |

## Side by side comparison of programs

![side-by-side comparison of programs](https://i.imgur.com/Fj3NsDy.png)

Note that

* Rust doesn't explicitly mention the type.
* Rust doesn't require the format specifiers (e.g. `%d`).
* Rust requires to opt-in to mutability with `mut` keyword.
* Rust uses snake_case for variable names, while C uses camelCase.
