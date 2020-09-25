<template>
  <div class="home">
    <hello-world msg=".."/>
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

      <b-container>
        <b-row class="my-1">
          <b-col md="3">
            <b-form-input :state="null" placeholder="no validation"></b-form-input>
          </b-col>
          <b-col md="3">
            <b-form-input :state="false" placeholder="invalid state"></b-form-input>
          </b-col>
          <b-col md="3">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Doloremque, pariatur quidem. Sit molestias rerum et laudantium ipsam minima iste amet error laboriosam fugiat? Reprehenderit cupiditate ipsam vero quod voluptatum soluta?
          </b-col>
          <b-col md="3">
            <b-form-input id="input-valid" :state="true" placeholder="valid input"></b-form-input>
          </b-col>
        </b-row>
        <b-row>
          <b-col sm="12">
            <b-form-group>
              <b-form-input v-model="message" :state="true">
              </b-form-input>
              <b-alert variant="success" show>Message: {{ message }}</b-alert>
            </b-form-group>
          </b-col>
        </b-row>

        <b-row>
          <b-col sm="4">
            <b-form-checkbox v-model="checked">nam</b-form-checkbox>
            <b-alert variant="danger" show>{{ checked }}</b-alert>
          </b-col>
        </b-row>

        <b-row>
          <zoom @re-size="handleZoomClick" :fontsize="size" v-for="(post, index) in posts" :key="index" :post="post"></zoom>
        </b-row>

        <b-row>
          <button-counter></button-counter>
          <button-counter></button-counter>
          <button-counter></button-counter>
          <button-counter></button-counter>
          <button-counter></button-counter>
        </b-row>
        <b-row>
          <b-col sm='4'>
            <custom-input v-model="name"></custom-input>
            your text : {{ name }}
          </b-col>
        </b-row>
        <b-row>
          <b-col sm="10">
            <slot-custom>
              <ul slot="header">
                <li>home</li>
                <li>contact</li>
                <li>about</li>
              </ul>
              Lorem ipsum, dolor sit amet consectetur adipisicing elit. Accusantium aliquam vero tempora reiciendis explicabo, quos ab magni eum, maxime odio maiores, molestiae neque fuga praesentium esse! Numquam hic quam sunt?

{{ size }}
              <footer slot="footer">
                content foooter
              </footer>
              </slot-custom>
          </b-col>
        </b-row>
      </b-container>

    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Zoom from '@/components/Zoom.vue'
import ButtonCounter from '@/components/ButtonCounter.vue'
import CustomInput from '@/components/CustomInput.vue'
import SlotCustom from '@/components/Slot.vue'

export default {
  name: 'Home',
  data () {
    return {
      message: 'home page',
      checked: true,
      size: 20,
      posts: [
        { title: 'Some quick example text to build on the card title and make up the bulk of the card1s content. 1', id: 1 },
        { title: 'Some quick example text to build on the card title and make up the bulk of the card1s content. 2', id: 2 },
        { title: 'Some quick example text to build on the card title and make up the bulk of the card1s content. 3', id: 3 },
        { title: 'Some quick example text to build on the card title and make up the bulk of the card1s content. 4', id: 4 },
        { title: 'Some quick example text to build on the card title and make up the bulk of the card1s content. 5', id: 5 },
        { title: 'Some quick example text to build on the card title and make up the bulk of the card1s content. 6', id: 6 }
      ],
      name: ''
    }
  },
  components: {
    HelloWorld,
    Zoom,
    ButtonCounter,
    CustomInput,
    SlotCustom
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
    },
    handleZoomClick (param) {
      if (param === 1) {
        this.size++
      } else {
        this.size--
      }
    }
  }
}
</script>
