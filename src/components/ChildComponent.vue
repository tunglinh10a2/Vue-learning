<template>
  <div class="child">
    <li>{{ todo.text }}</li>
  </div>
</template>

<script>
    export default {
        name: "ChildComponent",
        props: ['todo']
    }
</script>

<style scoped>

</style>
