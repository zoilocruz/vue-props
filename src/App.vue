<template>
  <div id="app">
    <app-header v-bind:title="title" v-on:changeEmit="updateTitle($event)"></app-header>
    <app-ninjas v-bind:ninjas="ninjas"></app-ninjas>
    <app-footer v-bind:title="title"></app-footer>
    <app-vueslots>
      <h2 slot="title">{{ title }}</h2>
      <p slot="text">this is a sample slots</p>
    </app-vueslots>
    <!--<img src="./assets/logo.png">
    <router-view/>-->
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Ninjas from './components/Ninjas.vue'
import VueSlots from './components/VueSlots'

export default {
  name: 'App',
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-ninjas': Ninjas,
    'app-vueslots': VueSlots

  },
  data: function () {
    return {
      ninjas: [
        {name: 'Ryu', speciality: 'Vue Component', show: false},
        {name: 'Crystal', speciality: 'HTML Wizardry', show: false},
        {name: 'Hitoshi', speciality: 'Click Events', show: false},
        {name: 'Tango', speciality: 'Conditional', show: false},
        {name: 'Kami', speciality: 'Webpack', show: false},
        {name: 'Yoshi', speciality: 'Data Diggin', show: false}
      ],
      title: 'Vue Sample fdgdfg'
    }
  },
  methods: {
    updateTitle: function (event) {
      this.title = event
    }
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  //margin-top: 60px;
}
</style>
