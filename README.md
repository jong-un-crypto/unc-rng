# NEAR-RNG
#### This is a fork of tiny-rng https://github.com/JohnBSmith/tiny-rng to work with smart contract of the NEAR protocol to minimize the binary size of the wasm

Warning: Not cryptographically secure.

Examples:
```rust
let mut rng = Rng::new(env::random_seed());
rng.rand_range_u32(0, 20)
```