**Reproducer for Carbon Charts Svelte breaking Carbon Components Svelte's PasswordInput.**

Run this with:

```
$ pnpm install
$ pnpm run dev
```

Problematic CSS import is performed line 15 in App.svelte

- With it, passwordinput's show password button is broken, chart works correctly
- Without it, passwordinput's show password button works, chart is broken

