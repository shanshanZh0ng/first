<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
    <!-- <NameList></NameList>
    <Input></Input>
    <LogIn></LogIn> -->
    <router-link to="login" tag="a">login</router-link>
    <router-link to="input" tag="a">input</router-link>
    <router-link to="/" tag="a">/..</router-link>
  </div>
</template>

<script>
import NameList from '@/components/NameList';
import Input from '@/components/Input';
import LogIn from '@/components/LogIn';

export default {
  name: 'App',
  components: {
    NameList,
    Input,
    LogIn
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
