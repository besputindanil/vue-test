<template>
  <div id="app">
    <name-input @onNameInputEnter="pushName"/>
    <name-list :names="names"/>
    <random-name :names="names"/>
  </div>
</template>

<script>
import NameInput from './components/NameInput.vue'
import NameList from './components/NameList.vue'
import RandomName from './components/RandomName.vue'

export default {
  name: 'App',
  components: {
    NameInput,
    NameList,
    RandomName
  },
  data: function() {
    return {
      names: []
    }
  },
  methods: {
        pushName: function(data) {
            this.names.push(data);
        }
    }
}
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100vh;
  
  font-family: Helvetica, Arial, sans-serif;
  color: #2c3e50;
}
</style>
