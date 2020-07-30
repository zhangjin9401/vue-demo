<!--
 * @Author: your name
 * @Date: 2020-07-29 11:16:30
 * @LastEditTime: 2020-07-29 14:47:46
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /vue-demo/src/components/oneCard.vue
--> 
<template>
  <div class="one-card">
    <!-- <h2 v-if="obj.b && obj.b.color">我接受到的是 {{obj.b.color}}</h2> -->
    <h2 v-if="obj.b && obj.b.color && obj.b.color[0] === 'green'">是绿色呢</h2>
    <h2 v-else>不是绿色</h2>
    <!-- <h2 v-if="obj2 && obj2.age === 22">我接受到的obj2是age22的 {{obj2}}</h2>
    <h2 v-else>我接受到的obj2非非非 {{obj2}}</h2> -->
  </div>
</template>

<script>
export default {
  props: {
    obj: {
      type: Object,
      default: () => {
        return {}
      }
    },
     obj2: {
      type: Object,
      default: () => {
        return {}
      }
    }
  },
  watch:{
    obj:{
      handler(newVal){
        console.log('有新值', newVal)
      },
      immediate: true,
      deep:true
    }
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
