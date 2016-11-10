<template>
  <button @click.prevent="$parent.$refs[target].toggleVisibility()">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'HexToggle',

    props: {
      target: String,
    },
  }
</script>
