<template>
  <div id="app">
    <validate-component num="1">
      <some-component>
        <validate-component num="2"></validate-component>
      </some-component>
      <some-component>
        <validate-component num="3">
          <validate-component num="4" />
        </validate-component>
      </some-component>
      <validate-component num="5"></validate-component>
    </validate-component>
  </div>
</template>

<script>
import ValidateComponent from "./components/ValidateComponent.vue";
import SomeComponent from "./components/SomeComponent";

export default {
  name: "App",
  components: {
    ValidateComponent,
    SomeComponent,
  },
};
</script>
