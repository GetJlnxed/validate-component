<template>
  <div>
    <div class="display">
      <button @click="validate">Validate</button>
      <p>---{{ num }}</p>
    </div>

    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "ValidateComponent",
  props: {
    num: {
      type: String,
      required: true,
    },
  },
  methods: {
    validate() {
      console.log(`validating - ${this.num}`);
      this.$children.forEach((child) => {
        child.validate();
      });
    },
  },
};
</script>

<style scoped>
.display {
  display: flex;
  flex-flow: row nowrap;
}
</style>
