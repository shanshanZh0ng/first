<template>
  <div class="hello">
    <p>{{msg}}</p>
    <p>{{reversedMsg}}</p>
    <button @click="reverseMsg">翻转msg</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  computed: {
    reversedMsg () {
      return this.msg.split('').reverse().join('');
    }
  },
  methods: {
    reverseMsg () {
      this.msg = this.msg.split('').reverse().join('');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .hello {
    border: 1px solid lawngreen
  }
</style>
