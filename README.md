# Rust and C: equivalents and differences

This is a collection of side-by-side comparisons of Rust and C code snippets, with an emphasis on the differences between the two languages.

It was written with the intention to identify the smallest yet most capable subset of Rust, so that teaching Rust could be simplified to the level of C.

The result of such approach is that the learners of Rust will first learn unidiomatic, unsafe but still valid Rust, and then gradually learn the idiomatic Rust as they progress.

Coincidentally, it can be a great introduction to Rust for C programmers.

## Note on the order of the comparisons

In order to avoid the repetition of the same concepts, the comparisons are ordered in such a way that the concepts are introduced only once, and then reused in the subsequent comparisons.

## Note on many ways to do the same thing

Both Rust and C can often do the same thing in many different ways. For simplicity, **this document will try its best to show only one way to do something, and will not attempt to show all the alternatives**. This includes the alternatives that would make the code considerably simpler. Those can be learned from ground up. However, it will demonstrate ways to do something simpler if it has a great impact on the delivery of the learning material.
