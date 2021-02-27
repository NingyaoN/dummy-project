<template>
  <div class="wrapper">
    <div class="item">
      <DeclarativeRendering />
    </div>
    <div class="item">
      <ComputedProperties />
    </div>
    <div class="item">
      <ClassAndStyleBindings />
    </div>

    <div class="item">
      <UsingCustomButtonComponent />
    </div>

    <div class="item">
      <ConditionalRendering />
    </div>
    <div class="item">
      <ListRendering />
    </div>
    <div class="item">
      <FormSelectHandling />
    </div>
    <div class="item">
      <alert-box v-if="error">
        This is message from parent filling the slot
      </alert-box>
      <button style="margin-top: 10px" @click="showError">
        {{ getLabel }}
      </button>
    </div>
    <div class="item">
      <Tabs />
    </div>
    <div class="item">
      <ComponentInDepth header="Im the props send from parent App.vue" />
    </div>
  </div>
</template>

<script>
import DeclarativeRendering from './components/declarative-rendering.vue';
import ComputedProperties from './components/computed-properties.vue';
import ClassAndStyleBindings from './components/class-style-bindings.vue';
import UsingCustomButtonComponent from './components/using-button-component.vue';
import ConditionalRendering from './components/conditional-rendering.vue';
import ListRendering from './components/list-rendering.vue';
import FormSelectHandling from './components/form-handling.vue';
import AlertBox from './components/alert-box.vue';
import Tabs from './components/tabs.vue';
import ComponentInDepth from './components/component-in-depth.vue';

export default {
  name: 'App',
  components: {
    DeclarativeRendering,
    ComputedProperties,
    ClassAndStyleBindings,
    UsingCustomButtonComponent,
    ConditionalRendering,
    ListRendering,
    FormSelectHandling,
    'alert-box': AlertBox,
    Tabs,
    ComponentInDepth,
  },

  data() {
    return {
      error: false,
    };
  },
  computed: {
    getLabel() {
      return this.error ? 'HIDE ERROR' : 'SHOW ERROR';
    },
  },
  methods: {
    showError() {
      this.error = !this.error;
    },
  },
};
</script>

<style>
.wrapper {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  box-shadow: 1px 1px 1px 2px gray;
  border-radius: 2px;
  justify-content: space-between;
  align-items: center;
}

.item {
  width: calc(100% / 3);
  margin: 10px;
  padding: 30px;
  box-shadow: 1px 1px 1px black;
  justify-content: center;
  align-self: center;
}
</style>
