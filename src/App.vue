<template>
  <div id="app">
    <hex-toggle target="myToggle" class="toggle">Toggle</hex-toggle>
    <hex-toggle-panel ref="myToggle">
      <p>Invisible at creation.</p>
    </hex-toggle-panel>


    <hr>


    <hex-toggle target="myOtherToggle" class="toggle">Other Toggle</hex-toggle>
    <hex-toggle-panel ref="myOtherToggle" visible>
      <p>Visible at creation.</p>
    </hex-toggle-panel>


    <hr>


    <div class="accordion">
      <hex-toggle target="accordion-1-1" accordion="sample" class="toggle accordion-tab">One</hex-toggle>
      <hex-toggle-panel ref="accordion-1-1" visible class="accordion-panel">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
      </hex-toggle-panel>
    </div>

    <div class="accordion">
      <hex-toggle target="accordion-1-2" accordion="sample" class="toggle accordion-tab">Two</hex-toggle>
      <hex-toggle-panel ref="accordion-1-2" class="accordion-panel">
        <p>Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
      </hex-toggle-panel>
    </div>

    <div class="accordion">
      <hex-toggle target="accordion-1-3" accordion="sample" class="toggle accordion-tab">Three</hex-toggle>
      <hex-toggle-panel ref="accordion-1-3" class="accordion-panel">
        <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip.</p>
      </hex-toggle-panel>
    </div>


    <hr>


    <div class="accordion">
      <hex-toggle target="accordion-2-1" accordion="sample-2" class="toggle accordion-tab">One</hex-toggle>
      <hex-toggle-panel ref="accordion-2-1" class="accordion-panel">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
      </hex-toggle-panel>
    </div>

    <div class="accordion">
      <hex-toggle target="accordion-2-2" accordion="sample-2" class="toggle accordion-tab">Two</hex-toggle>
      <hex-toggle-panel ref="accordion-2-2" class="accordion-panel">
        <p>Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
      </hex-toggle-panel>
    </div>

    <div class="accordion">
      <hex-toggle target="accordion-2-3" accordion="sample-2" class="toggle accordion-tab">Three</hex-toggle>
      <hex-toggle-panel ref="accordion-2-3" class="accordion-panel">
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




<style>
  .toggle::after {
    content: '+';
  }

  .is-open::after {
    content: '-';
  }
</style>
