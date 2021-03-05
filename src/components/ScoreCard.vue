<template>
  <div>
    <h2>{{ score }}</h2>
    <div>
        <button @click="addPoint">+</button>
        <button @click="subtractPoint">-</button>
    </div>
  </div>
</template>

<script>
export default {
    props: ["score"],

    methods: {
        addPoint() {
        this.$emit("pointAdded");
        },
        subtractPoint() {
        this.$emit("pointSubtracted");
        },
    },
}
</script>

<style>

</style>