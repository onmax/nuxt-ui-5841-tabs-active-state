# nuxt-ui issue 5841 repro

Small repro for a `UTabs` active state problem.

## Steps

```bash
pnpm install
pnpm dev
```

Open the local app.

## What it does

- Server renders one tab: `SKU`
- Client hydrates with `v-model` still set to `product_sku`
- Client items are:
  - `Product Group`
  - `Category`
  - `SKU`

## Expected

Only `SKU` should be active after hydration.

## Observed

Two tabs become active after hydration:

- `Product Group`
- `SKU`

This looks related to [nuxt/ui#5841](https://github.com/nuxt/ui/issues/5841), which points at `:key="index"` in `UTabs`.
