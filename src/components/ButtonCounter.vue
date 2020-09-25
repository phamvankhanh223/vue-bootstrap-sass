<template>
  <div>
    <b-button variant="outline-success" @click="count++">you click {{count}} times</b-button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      count: 0
    }
  }
}
</script>

<style>

</style>
