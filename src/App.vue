<!--
 * @Author: your name
 * @Date: 2020-07-29 11:16:30
 * @LastEditTime: 2020-07-30 10:48:17
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /vue-demo/src/App.vue
--> 
<template>
  <div id="app">
    <!-- vue不能检测到对象属性的添加或删除 -->
    <!-- <one-card :obj="obj" :obj2="obj2"></one-card> -->
    <h1 v-if="obj1 && obj1.a">obj1.a{{obj1.a}}</h1>
    <h1 v-if="obj1 && obj1.b">obj1.b{{obj1.b}}</h1>
    <h1 v-if="obj1">obj1{{obj1}}</h1>
    <button @click="setObj1a">给obj1添加属性a</button>
    <button @click="setObj1b">给obj1添加属性b</button>
    <button @click="setObj1ab">更改obj1添加属性ab</button>
    <button @click="againSetObj1ab">再次更改obj1添加属性ab</button>
    <button @click="againSetObj1abTwo">再次第二次更改obj1添加属性ab</button>
    <button @click="againSetObj1abThree">再次第三次更改obj1添加属性ab</button>
  </div>
</template>

<script>
// import oneCard from './components/oneCard.vue'

export default {
  name: 'App',
  components: {
    // oneCard
  },
  data(){
    return{
      obj1:{

      },
      obj:{
        b:{}
      },
      obj2:{}
    }
  },
  methods:{
    setObj1a(){
      // this.obj1.a = 'hello obj1 a'
      this.obj1 = Object.assign({},{a:'hello obj1 a'})
    },
    setObj1b(){
      // this.obj1.a = 'hello obj1 a'
      this.obj1 = Object.assign({},{b:'hello obj1 b'})
    },
    setObj1ab(){
      this.obj1 = Object.assign({},{a:'a',b:'b'})
    },
    againSetObj1ab(){
      this.obj1 = Object.assign({},{
        a:{
          a1:'a1',
          a2:'a2'
        },
        b:{
          b1:{
            b10:['green']
          }
        }
      })
    },
    againSetObj1abTwo(){
      this.obj1 = Object.assign({},{
        a:{
          a1:'a1',
        },
        b:{
          b1:{
            b10:[]
          }
        }
      })
    },
    againSetObj1abThree(){
      
    },
    createB(){
      // this.obj.b = 2
      this.obj = {a:4,b:{
        name:'bob',
        color:['red']
      }}
      this.obj2 = {name:'amy', age:22}
    },
    changeB(){
      // this.obj.b.color = ['green']
      this.obj = Object.assign({},{b:{color:['green']}})
      // this.$set(this.obj,'b',{color:['green']})
    },
    changeB2(){
      this.obj = Object.assign({},{b:{color:['red']}})
    },
    changeObj2(){
       this.obj2 = {name:'amy18', age:18}
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
