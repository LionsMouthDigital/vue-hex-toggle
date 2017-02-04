<template>
  <button @click.prevent="togglePanel()" :class="{ 'is-open': targetPanelIsOpen }">
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


    data() {
      return {
        targetPanelIsOpen: false,
      };
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
      checkIfTargetPanelIsOpen() {
        if (typeof this.$parent.$refs[this.target] === 'undefined') {
          return false;
        }

        return this.$parent.$refs[this.target].show;
      },

      /**
       * Toggle the target panel.
       */
      togglePanel() {
        // this.$el.classList.toggle('is-open');
        // HexBus.$emit('HexToggle:toggled', this.targetPanel._uid, this.accordion);
        HexBus.$emit('HexToggle:toggled', this)
        this.targetPanelIsOpen = !this.targetPanelIsOpen;
      },

      /**
       * Close the target panel.
       */
      closePanel() {
        HexBus.$emit('HexToggle:panelClosed', this);
        this.targetPanelIsOpen = false;
      },
    },


    created() {
      HexBus.$on('HexToggle:toggled', (toggledToggle) => {
        if (this.accordion) {
          // If:
          //  1. this is NOT the clicked toggle and
          //  2. this is part of the SAME accordion...
          if (toggledToggle._uid !== this._uid && toggledToggle.accordion === this.accordion) {
            this.closePanel();
          }
        }
      });
    },


    mounted() {
      // Ensure `targetPanelIsOpen` is accurate.
      // This should almost certainly be an event emitted by `HexTogglePanel`, but it's late and I'm
      // getting tired and thirsty ¯\_(ツ)_/¯.
      this.targetPanelIsOpen = this.targetPanel.show;
    },
  }
</script>
