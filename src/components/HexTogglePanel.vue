<template>
  <div v-show="show || useClass">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'HexTogglePanel',


    props: {
      // Use a class rather than `v-show`. This greatly simplifies breakpoint-based visibility.
      useClass: Boolean,
      // Show when page loads.
      visible:  Boolean,
    },


    data() {
      return {
        // Show this panel?
        show: false,
      };
    },


    methods: {
      /**
       * Toggle the visibility of the panel.
       *
       * @author Curtis Blackwell
       * @return {void}
       */
      toggleVisibility() {
        // The Vue way.
        if (!this.useClass) {
          this.show = !this.show;

        } else {
          // The class-y way. ಠ_ರೃ
          this.$el.classList.toggle('hidden');
        }
      },
    },


    created() {
      // Show when the page loads if `visible` prop passed.
      if (this.visible) {
        this.show = true;
      }

      // Toggle visibility when targeting tab gets clicked.
      HexBus.$on('HexToggle:toggled', (uid) => {
        // If this is the targeted panel, toggle it.
        if (uid === this._uid) {
          this.toggleVisibility();
        }
      });

      // Close panel when targeting tab says to.
      // Useful when tab (other than targeting tab) from accordion gets clicked.
      HexBus.$on('HexToggle:panelClosed', (uid) => {
        // If this is the targeted panel, close it.
        if (uid === this._uid) {
          this.show = false;
        }
      });
    },
  }
</script>
