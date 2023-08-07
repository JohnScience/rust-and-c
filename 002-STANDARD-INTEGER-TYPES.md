# Comparison of programs with standard integer types

In this context, "standard integer types" are either

* *standard signed integer types*, which are `signed char`, `short int`, `int`, `long int`, and `long long int`, or
* *standard unsigned integer types*, which are `unsigned char`, `unsigned short int`, `unsigned int`, `unsigned long int`, and `unsigned long long int`

as defined in the [C standard](https://www.open-std.org/jtc1/sc22/wg14/www/docs/n1256.pdf) (6.2.5, page 33). Since C was created at the time when 8-bit bytes were not yet ubiquitous, they are not even required to be `8*2^n`-bit wide, though in practice they nearly always are. Precise sizes of these types are implementation-defined, but the C standard often has more to say about each of them.

C has become so influential that its types are often used in other languages as well, for example, for the purpose of interoperability.

## On declarations and definitions

Previously, we defined and initialized a variable in two statements. However, it is considerably more common to do both in a single statement. This is important so that we could fit more code on a single screen.

| C | Rust | Comparison |
|---|---|---|
|  | use std::ffi::*; | Unlike in C, using standard integer C types in Rust requires importing them from the ffi module. It is because the "default" alternative to them in Rust is fixed-sized types like u32, i8, and so on. They are akin to fixed-sized types from <stdint.h> header. Rust also provides usize and isize word/pointer-size types for indexing but it works out fine because unlike in C, Rust forbids notoriously error-prone implicit type conversions. Usage of fixed-sized types is especially important today because the sending and the receiving ends in the communication might not agree about the size of int and it can cause problems. Nowadays, usage of types whose size is implementation-dependent does not improve but often hinders the portability of the code. |
| signed char short int int long long long | c_schar c_short c_int c_long c_longlong | Rust's way to refer to the standard integer C types are shorter while remaining just as readable. Even though due to the use of let keyword the gains are not as noticeable, let keyword greatly simplifies parsing of Rust code and makes writing code with more complex types much simpler. |
| unsigned char unsigned short unsigned int unsigned long unsigned long long | c_uchar c_ushort c_uint c_ulong c_ulonglong | ditto |
| %hhd %hd %d %ld %lld %hhu %hu %u %lu %llu | {} | Thanks to the powerful macro system, Rust can greatly simplify the printing of various values. In Rust, you rarely if ever have to worry about specifying the formatting. And when you do, you don't have to manually do this. Notably, difficult formatting specifiers are some of the reasons why fixed-width integers are less common in C. |
| printf("...\n"); | println!("..."); | Rust has a println macro that automatically appends a newline character at the end of the line. In C, you have to use printf and manually add a newline character at the end of the line. This can make reading the literal text easier by removing the visual clutter in the form of newline character ("\n") part. |

## Side by side comparison of programs

![side-by-side comparison of programs](https://i.imgur.com/rsL9h3y.png)

Note that:

* Without fitting definitions and initializations on a single line, it wouldn't be possible to fit the programs on a single screen.
* Rust promotes the use of more robust and inuitive fixed-width types.
* Type names for standard integer types are shorter in Rust.
* Rust simplifies printing of values.
* Rust simplifies reading of literal text by providing a macro that automatically appends a newline character at the end of the line.
