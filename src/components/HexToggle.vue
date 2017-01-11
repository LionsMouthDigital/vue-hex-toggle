<template>
  <button @click.prevent="togglePanel()">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'HexToggle',


    props: {
      target: String,
    },


    computed: {
      /**
       * The target's _uid.
       *
       * @return {Number}
       */
      targetUid() {
        return this.$parent.$refs[this.target]._uid;
      }
    },


    methods: {
      /**
       * Activate the associated tab panel.
       */
      togglePanel() {
        HexBus.$emit('HexToggle:toggled', this.targetUid);
      },
    },
  }
</script>
