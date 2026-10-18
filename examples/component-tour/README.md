# component-tour

A small tour of Lux's component features: props, slots, scoped styles, conditional rendering, list rendering.

```bash
lux check Tour.lux
lux build Tour.lux --target wasm -o tour
python3 -m http.server -d tour 8080   # open http://localhost:8080

lux dev Tour.lux                      # or: live-reload dev server
```

What this shows:
- Component composition (`TaskRow` renders a `Badge`; the app nests both inside `Card`)
- Props passed as `name=value`, including values from a `for` binding (`name=task.name`)
- Slots: content nested under `Card title="...":` renders where `slot` sits in `Card`'s view
- Scoped `style` blocks declared inside a component, compiled to `.name[data-lux-scope="Component"]` selectors
- `if`/`else` and `for` in view blocks, including an `if` on a signal that re-renders when a button flips it
- An `if` inside a `for` that mixes a signal with the loop variable (`if show_done or not task.done:`), so a button filters the list

Notes:
- Needs lux 0.2.1 or later (`cargo binstall openie-lux`). With lux 0.2.0 the filter button has no effect, scoped styles don't apply under `--target html`, and `lux dev` leaves them out.
- `lux run Tour.lux` executes the program and prints an energy receipt; it doesn't render the view.
- Props are untyped here. The parser accepts `name: Type = default` in a component's parameter list, but no checked Lux example exercises it yet, so the tour doesn't rely on it.
