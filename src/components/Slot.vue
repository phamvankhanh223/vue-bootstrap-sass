<template>
  <div>
    <slot name="header"></slot>
    <slot>content hear</slot>
    <div style="background:yellow">
      <slot name="another-slot">another slot {{ data_test }}</slot>
    </div>
    <slot name="footer"></slot>
  </div>
</template>

<script>
export default {
  data () {
    return {
      data_test: 'test data slot'
    }
  }
}
</script>

<style>

</style>
