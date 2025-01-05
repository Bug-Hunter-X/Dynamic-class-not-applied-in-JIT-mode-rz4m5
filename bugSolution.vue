The most effective solution depends on your setup and whether you're using JIT mode.  Here are two options:

**1. Purge option for non-JIT mode:**

If you are not using JIT mode then add the classes you intend to use to the purge option in your `tailwind.config.js`
```javascript
module.exports = {
  purge: {
    content: ['./src/**/*.html', './src/**/*.vue', './src/**/*.js'],
    // ...other config
  },
};
```

**2. `@apply` directive (JIT mode):**

For JIT mode,  directly apply the styles instead of relying on class names:
```vue
<template>
  <div class="bg-blue-500 @apply text-white">Dynamic Content</div>
</template>
```

**3. Workaround (JIT mode, Adding to existing element):**

Instead of adding a new class, modify the existing classes of an element:
```vue
<template>
  <div ref="myDiv" class="bg-blue-500 text-white">Dynamic Content</div>
</template>

<script>
export default {
  data() {
    return {

    };
  },
  mounted(){
    this.$nextTick(() => {
          this.$refs.myDiv.classList.add('text-red-500');
    })
  }
};
</script>
```
Choose the approach that best fits your project's structure and preferences.