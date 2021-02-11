<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "SomeComponent",
  methods: {
    validate() {
      console.log("wrong validate");
    },
  },
};
</script>
