<template>
  <button @click.prevent="$parent.$refs[target].show = !$parent.$refs[target].show">
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
