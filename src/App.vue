<template>
  <div id="app" class="app">
    <div class="app__wrapper">
        <name-input @onNameInputEnter="pushName"/>

      <div class="app__lists" v-if="showList">
        <name-list :names="names" @onClearList="onClearList"/>
        <random-name :names="names"/>
      </div>
      <div v-else>
        Список пуст
      </div>
    </div>
    
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
  data() {
    return {
      names: [],
    }
  },
  computed: {
    showList() {
      return this.names.length ? true : false
      // if (this.names.length) {
      //   return this.isShow;
      // }
    }
  },
  methods: {
        pushName(data) {
            this.names.push(data);
        },
        onClearList() {
          return this.names = [];
        }
        
    }
}
</script>

<style>
.app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  
  width: 100%;
  height: 100vh;
  
  font-family: Helvetica, Arial, sans-serif;
  font-size: 14px;
  line-height: 16px;
  color: #5D0F4C;

  background-color: #FFC9AA;
}

.app__wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    max-width: 500px;
    min-height: 500px;
    padding: 20px;

    background-color: #7AB85C;
    border-radius: 2px;
  }

.app__lists {
  display: flex;
  align-items: flex-start;
}

.app-list {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 0;
  margin-bottom: 20px;
  padding-left: 0;

  list-style: none;
}

.button {
  margin-bottom: 20px;
  padding: 15px;

  background: transparent;
  background-color: #9B4D89;
  outline: none;
  border: none;
  border-radius: 4px;

  color: #FFC9AA;
  text-transform: uppercase;

  cursor: pointer;

  transition: .3s ease;
}

.button:hover,
.button:focus {
  opacity: .8;
}
</style>
