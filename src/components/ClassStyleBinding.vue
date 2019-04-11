<template>
  <div id="style-binding">
    <div>Object syntax</div>
    <div class="static" v-bind:class="{active: isActive, 'text-danger': hasError}">
      Class style binding
    </div>
    <div class="static" v-bind:class="classObject">
      Class object
    </div>

    <div class="static" v-bind:class="classObjectComputed">
      Class object computed
    </div>
    <br><br><br><br><br>

    <hr>
    <div>Array syntax</div>
    <div class="static" v-bind:class="[activeArrayClass, errorArrayClass]">Normal array syntax</div>
    <div class="static" v-bind:class="[isActive ? activeArrayClass : '', errorArrayClass]">Toggle condition in array</div>
    <div class="static" v-bind:class="[{ activeArrayClass: isActive}, errorArrayClass]">Object syntax in array syntax</div>
  </div>
</template>

<script>
    export default {
        name: "ClassStyleBinding",
        data: function () {
          return {
              // Object syntax
              isActive: true,
              error: false,
              hasError: true,

              classObject: {
                  active: true,
                  'text-danger': false
              },

              // Array syntax
              activeArrayClass: 'active',
              errorArrayClass: 'text-danger',
          }
        },
        computed: {
            classObjectComputed: function () {
              return {
                  active: this.isActive && !this.error,
                  'text-danger': this.error && this.error.type === 'fatal'
              }
            }
        }
    }
</script>

<style scoped>
  .text-danger {
    color: #ff0000;
  }

  .active {
    background-color: antiquewhite;
    border: 2px solid;
    margin: 20px 0px;
  }
</style>
