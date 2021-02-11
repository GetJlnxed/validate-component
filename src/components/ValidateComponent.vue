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
      this.activateChildren(this.$children);
    },
    activateChildren(childrenArray) {
      childrenArray.forEach((child) => {
        if (child.$options._componentTag === "validate-component") {
          child.validate();
        }
        if (child.$children.length !== 0) {
          this.activateChildren(child.$children);
        }
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
