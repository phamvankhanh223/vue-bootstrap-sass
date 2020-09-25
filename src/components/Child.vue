<template>
  <div>
    <slot :posts="posts" :hello="hello"></slot>
  </div>
</template>

<script>
export default {
  data () {
    return {
      posts: [
        { title: 'title 1' },
        { title: 'title 2' },
        { title: 'title 3' }
      ]
    }
  },
  methods: {
    hello (messsage) {
      alert('hellow form child component ' + messsage)
    }
  }

}
</script>

<style>

</style>
