# VueUse Nuxt layer issue reproduction

In a Nuxt layer environment, VueUse's composables are not found in the sublayer when used in the base layer being extended. This example uses `useMousedPressed()` which does work as expected when running a dev server for the base layer but is not found when running a dev server for the sublayer

## Steps to reproduce

1. Install dependencies with `pnpm i` on both the `./base` and `./sublayer` projects
2. Run the dev server on the sublayer with `pnpm dev`
3. Navigate to the index page, e.g. `localhost:3000/`

Nuxt will display a 500 error that `useMousePressed is not defined`, referring to the use of `useMousePressed()` in `./base/pages/index.vue`

## Contrasting example

The `nuxt-lodash` module is also installed in the base layer. By disabling the code in `./base/pages/index.vue` pertaining to VueUse and running a dev server for the sublayer, the relevant Lodash function can be seen properly working