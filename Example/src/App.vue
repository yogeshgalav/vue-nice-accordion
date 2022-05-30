<template>
  <div id="app">
    <VueNiceAccordion
    class="mb-2"
        title="VueNiceAccordion"
      >
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit accusamus ducimus quaerat illo, incidunt nisi sunt perferendis est possimus dolores, recusandae dicta sapiente sequi esse, et provident earum voluptatibus ullam. </p>
      </VueNiceAccordion>
  </div>
</template>
<style>
.mb-2 {
    margin-bottom: 20px !important;
}
.text-disabled {
    color: #bdbdbd !important;
}
</style>

<script>
import VueNiceAccordion  from 'vue-nice-accordion'

export default {
  name: 'App',
  components: {
    VueNiceAccordion,
    // VueNiceTabs,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
