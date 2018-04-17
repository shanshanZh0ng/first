<template>
  <div class="list">
    <ul class="nameList">
      <li v-for="(name, index) in nameList" :key="index">{{index}}、{{name}}
        <button @click="delName(index)">删除</button>
      </li>
    </ul>
    <ul class="placeList">

    </ul>
    <p></p>
    <button @click="addName">添加新名</button>
  </div>
</template>

<script>
const newProvince = {name: '河北', capital: '石家庄'};

export default {
  data () {
    return {
      nameList: ['小红', '小明', '小钟', '小猴子'],
      placeList: [
        {name: '北京', capital: '北京'},
        {name: '山东', capital: '济南'},
        {name: '江苏', capital: '南京'},
        {name: '广东', capital: '广州'},
        {name: '福建', capital: '厦门'}
      ]
    }
  },
  computed: {
    
  },
  methods: {
    addName () {
      this.nameList.unshift("小翠");
    },
    delName (index){
      console.log(index)
      this.nameList.splice(index,1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .list{
    border: 1px solid lightcoral
  }
</style>