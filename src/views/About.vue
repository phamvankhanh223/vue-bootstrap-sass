<template>
  <div class="about">
    <h1>This is an about page</h1>
    <child v-slot="{ hello , posts }">
      <button @click="hello">button on child</button>
      <button @click="hellow">button on parent</button>
      <ul>
        <li @click="hello(post.title)" v-for="(post, index) in posts" :key="index">{{ post.title }}</li>
      </ul>
    </child>
  </div>
</template>
<script>
import Child from '@/components/Child.vue'
export default {
  data () {

  },
  components: {
    Child
  },
  methods: {
    hellow () {
      alert('hellow from parent')
    }
  }
}
</script>
