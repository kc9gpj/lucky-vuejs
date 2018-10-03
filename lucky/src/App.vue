<template>
  <div id="app">
    <div>
    <status-indicator active pulse></status-indicator>
    <avatar image="https://i.imgur.com/qoLJtSg.png" label="DH" size="96" color="orange" stateOnline="true" ></avatar>
    </div>

    <div>
    <status-indicator positive pulse></status-indicator>
    <avatar label="JL" size="96" color="green"></avatar>
    </div>

     <div>
    <status-indicator negative pulse></status-indicator>
    <avatar size="96" color="blue"></avatar>
    </div>
    
    <Avatar/>
  </div>
</template>

<script>
  import 'status-indicator/styles.css'

import Avatar from './components/ui-avatar'

export default {
  name: 'App',
  components: {
    Avatar
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
