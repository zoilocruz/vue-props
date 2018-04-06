<template>
  <p>{{ copyright }} {{ title }}</p>
</template>

<script>
import { bus } from '../main'
export default {
  name: 'Footer',
  props: {
    title: {
      type: String
    }
  },
  data: function () {
    return {
      copyright: 'Copyright 2018 Vue sample'
    }
  },
  created: function () {
    bus.$on('changeEmit', (data) => {
      this.title = data
    })
  }
}
</script>

<style scoped>
footer{
  background: #222;
  padding: 6px;
}
p{
  color: lightgreen;
  text-align: center;
}
</style>
