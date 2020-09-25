<template>
  <div>
    <button
       v-for="tab in tabs"
       :key="tab"
       class="['tab-button, {active: currentTab === tab}]"
       @click="currentTab = tab"
    >
    {{ tab }}
    </button>
    <keep-alive>
        <component :is="currentTabComponent" class="tab"></component>
    </keep-alive>
  </div>
</template>

<script>
import TabArchive from '@/components/TabArchive.vue'
import TabPosts from '@/components/TabPosts.vue'
export default {
  data () {
    return {
      currentTab: 'Posts',
      tabs: ['Posts', 'Archive']
    }
  },
  components: {
    TabArchive,
    TabPosts
  },
  computed: {
    currentTabComponent () {
      return 'tab-' + this.currentTab.toLowerCase()
    }
  }
}
</script>

<style>

</style>
