<template>
  <div id="app">
    <hex-toggle target="myToggle">Toggle</hex-toggle>
    <hex-toggle-panel ref="myToggle">
      <p>Invisible at creation.</p>
    </hex-toggle-panel>

    <hr>

    <hex-toggle target="myOtherToggle">Other Toggle</hex-toggle>
    <hex-toggle-panel ref="myOtherToggle" visible>
      <p>Visible at creation.</p>
    </hex-toggle-panel>
  </div>
</template>

<script>
import HexToggle      from './components/HexToggle.vue';
import HexTogglePanel from './components/HexTogglePanel.vue';

export default {
  name: 'app',

  components: {
    HexToggle,
    HexTogglePanel,
  },
}
</script>
