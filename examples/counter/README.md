# counter

A reactive counter with signal-driven state.

```bash
lux check Counter.lux
lux build --target html Counter.lux   # static HTML
lux build --target wasm Counter.lux   # index.html + app.wasm
```

What this shows:
- `app` block with a `view:` tree
- `signal()` for reactive state
- `on:click -> ...` event handlers
- `"{count}"` reactive text interpolation
