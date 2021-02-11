<template>
  <div id="app">
    <validate-component num="1">
      <div>
        <validate-component num="2"></validate-component>
      </div>
      <div>
        <validate-component num="3">
          <validate-component num="4" />
        </validate-component>
      </div>
      <validate-component num="5"></validate-component>
    </validate-component>
  </div>
</template>

<script>
import ValidateComponent from "./components/ValidateComponent.vue";

export default {
  name: "App",
  components: {
    ValidateComponent,
  },
};
</script>
