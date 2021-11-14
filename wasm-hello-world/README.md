# wasm-hello-world

Build with 

```
cargo build --target wasm32-unknown-unknown --release && wasm-gc target/wasm32-unknown-unknown/release/wasm_hello_world.wasm
```

The resulting wasm-file:

```
(module
  (type $t0 (func (param i32) (result i32)))
  (func $_start (type $t0) (param $p0 i32) (result i32)
    local.get $p0
    i32.const 1
    i32.add)
  (table $T0 1 1 funcref)
  (memory $memory 16)
  (global $__data_end i32 (i32.const 1048576))
  (global $__heap_base i32 (i32.const 1048576))
  (export "memory" (memory 0))
  (export "_start" (func $_start))
  (export "__data_end" (global 0))
  (export "__heap_base" (global 1)))
```

Run `python3 -m http.server 8082` and visit http://localhost:8082/

## References

- [Compiling Rust to WebAssembly: A Simple Example](https://depth-first.com/articles/2020/06/29/compiling-rust-to-webassembly-a-simple-example/)