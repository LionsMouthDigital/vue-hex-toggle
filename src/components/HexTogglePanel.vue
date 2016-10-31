<template>
  <div v-show="show">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'HexToggle',

    props: {
      visible: Boolean,
    },

    data() {
      return {
        show: false,
      };
    },

    created() {
      // Show when the page loads if `visible` prop passed.
      if (this.visible) {
        this.show = true;
      }
    },
  }
</script>
