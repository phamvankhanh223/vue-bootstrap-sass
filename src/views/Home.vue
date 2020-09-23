<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <hello-world msg="Welcome to Your Vue.js App"/>
 thong tin
    <div class="row">
      <div class="col-md-12"> <b-alert show>Default Alert</b-alert>
       </div>
      <div class="col-md-6">
        left
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto fugit iste veniam voluptate, magnam aut ad aperiam quo consequatur consequuntur esse eaque distinctio iure magni soluta possimus illo maiores et.
      </div>

      <div class="col-md-6">
        right
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Consectetur sequi, vel, asperiores laudantium voluptatem nesciunt, libero cum tenetur tempore modi mollitia nostrum doloremque suscipit deleniti quibusdam nobis reiciendis magni explicabo!
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo exercitationem doloremque nobis hic! Laborum, in ex sed et aut minima. Dolore recusandae fugit ex iure reprehenderit ipsum consequatur, incidunt asperiores.
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  data () {
    return {
      message: 'home page'
    }
  },
  components: {
    HelloWorld
  },
  mounted () {
    console.log('component mounted.')
  },
  created () {
    console.log('component created ')
  },
  methods: {
    handleClick () {
      console.log('hellow')
    }
  }
}
</script>
