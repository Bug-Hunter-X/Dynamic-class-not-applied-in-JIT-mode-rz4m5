# Dynamic Class Styling Issue in Tailwind CSS JIT Mode

This repository demonstrates a common issue encountered when using Tailwind CSS's JIT (Just-In-Time) mode with dynamically generated content in Vue.js.  Specifically, classes added after the initial page load may not be recognized by Tailwind, resulting in a lack of styling.

## Problem
The `bug.vue` file showcases a Vue component where a class (`dynamicClass`) is dynamically added to a `div`.  When using Tailwind's JIT mode, this dynamic class does not get styled correctly.

## Solution
The `bugSolution.vue` file presents a solution using `purge` option in Tailwind config for non-JIT mode. In the case of JIT mode, we can use the `@apply` directive to explicitly apply the styles or use a workaround involving adding classes to an existing element. 