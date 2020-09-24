<!--
 * @Author: your name
 * @Date: 2020-07-29 11:16:30
 * @LastEditTime: 2020-09-23 19:51:20
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /vue-demo/src/components/oneCard.vue
--> 
<template>
  <div class="one-card">
    <h1>one card~ {{oneCount.colors}}</h1>
  </div>
</template>

<script>
export default {
  props: {
    oneCount:{
      type: Object
    }
  },
  watch:{
  },
  created(){
    console.log('OneCard created')
  },
  mounted(){
    console.log('OneCard mounted')
  },
  destroyed(){
    console.log("哎呀～oneCard 被销毁了")
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
