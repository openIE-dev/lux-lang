# component-tour

A small tour of Lux's component features: props, slots, scoped styles, conditional rendering, list rendering.

```bash
lux check Tour.lux
lux build Tour.lux --target wasm -o tour
python3 -m http.server -d tour 8080   # open http://localhost:8080
```

What this shows:
- Component composition (`TaskRow` renders a `Badge`; the app nests both inside `Card`)
- Props passed as `name=value`, including values from a `for` binding (`name=task.name`)
- Slots: content nested under `Card title="...":` renders where `slot` sits in `Card`'s view
- Scoped `style` blocks declared inside a component, compiled to `.name[data-lux-scope="Component"]` selectors
- `if`/`else` and `for` in view blocks, including an `if` on a signal that re-renders when a button flips it

Notes (lux 0.2.0):
- Use the WASM build to see the page as intended. `lux build --target html` emits the scoped CSS but doesn't tag elements with `data-lux-scope`, so those styles don't apply there. `lux dev` tags the elements but leaves out the scoped CSS.
- `lux run Tour.lux` executes the program and prints an energy receipt; it doesn't render the view.
- Props are untyped here. The parser accepts `name: Type = default` in a component's parameter list, but no checked Lux example exercises it yet, so the tour doesn't rely on it.
