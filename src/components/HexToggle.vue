<template>
  <button @click.prevent="togglePanel()">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'HexToggle',


    props: {
      // Other panels with matching `accordion` values will all close.
      accordion: String,

      // Target panel's `ref`.
      target: {
        type:     String,
        required: true,
      },
    },


    computed: {
      /**
       * The target's _uid.
       *
       * @return {Number}
       */
      targetPanel() {
        return this.$parent.$refs[this.target];
      },
    },


    methods: {
      /**
       * Toggle the target panel.
       */
      togglePanel() {
        HexBus.$emit('HexToggle:toggled', this.targetPanel._uid, this.accordion);
      },

      /**
       * Close the target panel.
       */
      closePanel() {
        HexBus.$emit('HexToggle:panelClosed', this.targetPanel._uid);
      },
    },


    created() {
      // If this is an accordion, listen for `toggled` events.
      if (this.accordion) {
        HexBus.$on('HexToggle:toggled', (uid, accordion) => {
          // If:
          //  1. this is NOT the clicked toggle and
          //  2. this is part of the SAME accordion...
          if (uid !== this._uid && accordion === this.accordion) {
            this.closePanel();
          }
        });
      }
    },
  }
</script>
