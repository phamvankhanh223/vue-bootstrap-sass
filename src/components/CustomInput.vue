<template>
  <div>
    <input type="text" v-on:input="handleInput" :value="value">
    <div v-if="handleValidation">
        <b-alert show  variant="danger">Invalid value!</b-alert>
    </div>
  </div>
</template>

<script>
export default {
  props: ['value'],
  data () {
    return {
    }
  },
  methods: {
    handleInput ($event) {
      this.$emit('input', $event.target.value)
    }
  },
  computed: {
    handleValidation () {
      if (isNaN(this.value)) {
        return true
      }
      return false
    }
  }

}
</script>

<style>

</style>
