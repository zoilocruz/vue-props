<template>
  <header>
    <h1 v-on:click="changeTitle" v-on:dblclick="changeEmit">{{ title }}</h1>
  </header>
</template>

<script>
import { bus } from '../main'

export default {
  name: 'Header',
  props: {
    title: {
      type: String
    }
  },
  methods: {
    changeTitle: function () {
      this.title = 'Changed Title'
    },
    changeEmit: function () {
      // this.$emit('changeEmit', 'Vue changed emitted')
      this.title = 'Vue changed by bus'
      bus.$emit('changeEmit', 'Vue changed by bus')
    }
  }
}
</script>

<style scoped>
header {
  background: lightgreen;
  padding: 10px;
}
h1 {
  color: #222;
  text-align: center;
}
</style>
