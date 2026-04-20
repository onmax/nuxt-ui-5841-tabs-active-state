# nuxt-ui issue 5841 repro

Small repro for a `UTabs` active state problem.

## Steps

```bash
pnpm install
pnpm dev
```

Open the local app.

## What it does

- Server renders one tab: `Third`
- Client hydrates with `v-model` still set to `third`
- Client items are:
  - `First`
  - `Second`
  - `Third`

## Expected

Only `Third` should be active after hydration.

## Observed

Two tabs become active after hydration:

- `First`
- `Third`

This looks related to [nuxt/ui#5841](https://github.com/nuxt/ui/issues/5841), which points at `:key="index"` in `UTabs`.
