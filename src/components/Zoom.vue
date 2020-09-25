<template>
      <b-col sm="4" :style="{fontSize: size}">
        <b-button variant="outline-success" @click="handleReClick">Re (-)</b-button>
        <b-button variant="outline-danger" @click="handleIncClick">Inc (+)</b-button>
        fontsize:{{ size }}
        <b-card
          title="Card Title"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          img-top
          tag="article"
          class="mb-2"
        >
          <b-card-text>
            {{ post.title }}
          </b-card-text>

          <b-button href="#" variant="primary">Go somewhere</b-button>
        </b-card>
      </b-col>
</template>

<script>
export default {
  props: [
    'fontsize',
    'post'
  ],
  data () {
    return {

    }
  },
  mounted () {
    console.log('-----data post ', this.post)
  },
  computed: {
    size () {
      return this.fontsize + 'px'
    }
  },
  methods: {
    handleReClick () {
      this.$emit('re-size', -1)
    },
    handleIncClick () {
      this.$emit('re-size', 1)
    }
  }

}
</script>

<style>

</style>
