<!--
 * @Author: your name
 * @Date: 2020-07-29 11:16:30
 * @LastEditTime: 2020-09-24 10:13:02
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /vue-demo/src/App.vue
--> 
<template>
  <div id="app">
    <button @click="toggleOneCard">切换oneCrad</button>
    <button @click="addOneCount">oneCount自增</button>
    <button @click="shiftOneCount">oneCount自减</button>
    <one-card v-show="showOneCard" :one-count="oneCount"></one-card>
  </div>
</template>

<script>
import OneCard from './components/OneCard'
export default {
  name: 'App',
  components: {
    OneCard
  },
  data(){
    return{
      showOneCard: true,
      oneCount:{
        age:1,
        colors:{
          like:['r','e','d']
        }
      }
    }
  },
  created(){
    console.log('app created')
  },
  mounted(){
    console.log('app mounted')
  },
  methods:{
   toggleOneCard(){
     this.showOneCard = !this.showOneCard
    //  this.oneCount.colors.push('6')
   },
   addOneCount(){
     this.oneCount.colors.like.splice(3,0,'s')
   },
   shiftOneCount(){
     this.oneCount.colors.like[0] = 'g'
   }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
