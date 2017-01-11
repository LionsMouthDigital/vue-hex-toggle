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


    <hr>


    <div class="accordion">
      <hex-toggle target="accordion1" accordion="sample" class="accordion-tab">One</hex-toggle>
      <hex-toggle-panel ref="accordion1" visible class="accordion-panel">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
      </hex-toggle-panel>
    </div>

    <div class="accordion">
      <hex-toggle target="accordion2" accordion="sample" class="accordion-tab">Two</hex-toggle>
      <hex-toggle-panel ref="accordion2" class="accordion-panel">
        <p>Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
      </hex-toggle-panel>
    </div>

    <div class="accordion">
      <hex-toggle target="accordion3" accordion="sample" class="accordion-tab">Three</hex-toggle>
      <hex-toggle-panel ref="accordion3" class="accordion-panel">
        <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip.</p>
      </hex-toggle-panel>
    </div>
  </div>
</template>

<script>
import Components from './HexToggle.js';

export default {
  name: 'app',

  components: Components,
}
</script>
