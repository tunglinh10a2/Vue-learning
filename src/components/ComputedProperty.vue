<template>
  <div class="computed">
    <p>Original message: {{ message }}</p>
    <p>Computed reversed message: {{ reversedMessage }}</p>
    <p>Computed date time: {{ now }}</p>
  </div>
</template>

<script>
    export default {
        name: "ComputedProperty",
        data: function () {
          return {
              message: 'Hello',
          }
        },
        computed: {
          reversedMessage: function () {
              return this.message.split('').reverse().join('')
          },
          now: function () {
              return Date.now()
          }
        },
        methods: {
          reverseMessage: function () {
              return this.message.split('').reverse().join('')
          }
        }
    }
</script>

<style scoped>

</style>
