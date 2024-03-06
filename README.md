# UNC-RNG

#### This is a fork of tiny-rng https://github.com/JohnBSmith/tiny-rng to work with smart contract of the UNC protocol to minimize the binary size of the wasm

Warning: Not cryptographically secure.

Examples:

```rust
use unc_sdk::borsh::{self, BorshDeserialize, BorshSerialize};
use unc_sdk::{env, near_bindgen};
use unc_rng::{Rng};

unc_sdk::setup_alloc!();

#[near_bindgen]
#[derive(Default, BorshDeserialize, BorshSerialize)]
pub struct Counter {
    val: i32,
}

#[near_bindgen]
impl Counter {
  pub fn increment(&mut self) {
    let mut rng = Rng::new(&env::random_seed());
    let value = rng.rand_range_i32(0, 20);
    self.val += value;
  }
}
```
