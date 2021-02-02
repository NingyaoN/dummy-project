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
  </div>
</template>

<script>
import DeclarativeRendering from './components/declarative-rendering.vue';
import ComputedProperties from './components/computed-properties.vue';
import ClassAndStyleBindings from './components/class-style-bindings.vue';
import UsingCustomButtonComponent from './components/using-button-component.vue';

export default {
  name: 'App',
  components: {
    DeclarativeRendering,
    ComputedProperties,
    ClassAndStyleBindings,
    UsingCustomButtonComponent,
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
