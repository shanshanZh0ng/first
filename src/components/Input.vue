<template>
  <div class="input">
    <input type="text" placeholder="请输入" @keypress="toDoAddItem" v-model="msg">
    <button @click="toAddItem">确认</button>
    <p class="item" v-for="(item, index) in itemList" :key="index">{{index}}、{{item}}
      <button class="hide" @click="delItem(index)">删除</button>
    </p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: '',
      itemList : []
    }
  },
  methods: {
    toDoAddItem (e) {
      if(e.keyCode == "13"){
        this.itemList.unshift(this.msg);
        this.msg = "";
      }
    },
    toAddItem () {
      this.itemList.unshift(this.msg);
      this.msg = "";
    },
    delItem (index) {
      this.itemList.splice(index,1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .input{
    border: 1px solid saddlebrown;
  }
  .text {
    background: #ccc;
  }
  .text.highlight {
    background: pink;
  }
  .hide{display: none;}
  .item:hover .hide{display:inline-block;}
</style>