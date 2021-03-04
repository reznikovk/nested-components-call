<template>
  <div id="app">
      <validate-component name="1">
          <some-component>
              <div>
                  <validate-component name="2"></validate-component>
              </div>
          </some-component>
          <some-component>
              <validate-component  name="3">
                  <validate-component  name="4" />
              </validate-component>
          </some-component>
          <validate-component name="5"></validate-component>
      </validate-component>
  </div>
</template>

<script>
import ValidateComponent from './components/Validate.vue'
import SomeComponent from './components/Some.vue'

export default {
  name: 'App',
  components: {
      ValidateComponent,
      SomeComponent,
  }
}
</script>

<style>

</style>
