<template>
  <div id="dynamic-component-demo" class="demo">
    <button
      v-for="tab in tabs"
      v-bind:key="tab"
      v-bind:class="['tab-button', { active: currentTab === tab }]"
      v-on:click="currentTab = tab"
    >
      {{ tab }}
    </button>

    <component v-bind:is="currentTabComponent" class="tab"></component>
  </div>
</template>
<script>
import Home from './tab-components/home.vue';
import Archive from './tab-components/archive.vue';
import Posts from './tab-components/posts.vue';
export default {
  components: {
    'tab-home': Home,
    'tab-archive': Archive,
    'tab-posts': Posts,
  },
  data() {
    return {
      currentTab: 'Home',
      tabs: ['Home', 'Posts', 'Archive'],
    };
  },
  computed: {
    currentTabComponent() {
      return 'tab-' + this.currentTab.toLowerCase();
    },
  },
};
</script>
