<!--
 * @Author: your name
 * @Date: 2020-07-29 11:16:30
 * @LastEditTime: 2020-07-31 16:53:13
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
    <div v-for="(item, index) in arr1" :key="index">{{item}}</div>
    <button @click="addArr1">点击添加arr1属性</button>
    <button @click="delArr1">点击删除arr1属性</button>
    <button @click="changeArr1">点击更改arr1</button>
    <button @click="changeArr1Two">点击再次更改arr1</button>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      obj1:{

      },
      arr1:[{
        amy:{
          like:{
            sports:['run']
          }
        }
      }]
    }
  },
  methods:{
    addArr1(){
      this.arr1[0].amy.like.sports.push('ball')
    },

    delArr1(){
      this.arr1[0].amy.like.sports.shift()
    },

    changeArr1(){
      let newObj = {bob:{like:{sports:['ball']}}}
      this.arr1.push(newObj)
    },

    changeArr1Two(){
      // this.arr1[0].amy.cat = 'amity'
      // this.arr1.splice(0,1,{
      //   amy:{
      //     cat:'amity',
      //     like:{
      //       sports:['run']
      //     }
      //   }
      // })
      this.$set(this.arr1[0].amy,'cat','amity')
    },

    setObj1a(){
      // this.obj1.a = 'hello obj1 a'
      this.obj1 = Object.assign(this.obj1,{a:'hello obj1 a'})
      this.$set(this.obj1, 'a', 'hello obj1 a')
    },
    setObj1b(){
      // this.obj1.b = 'hello obj1 b'
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
