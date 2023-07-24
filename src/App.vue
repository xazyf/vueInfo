<template>
  <h1>用户信息展示</h1>
  <h2>姓名:{{person.name}}</h2>
  <h2 v-show="person.age">年龄:{{person.age}}</h2>
  <h2 v-show="person.sex">性别:{{person.sex}}</h2>
  <h2>爱好:{{person.hobby.join(' ')}}</h2>
  <button @click="addSex">添加性别信息</button>
  <button @click="deleteAge">删除用户年龄</button>
  <button @click="changeInfo">更改用户信息</button>
</template>
<script>
import {reactive, ref} from 'vue'
export default {
  name: 'App',
  setup(){
    let person=reactive({
      name:'小翠儿',
      age:18,
      hobby:['吃饭','睡觉','打豆豆']
    })
    function addSex(){
      person.sex='女'
      console.log(Object.prototype.toString.call(person.hobby[0]));
    }
    function deleteAge(){
      delete person.age
    }
    function changeInfo(){
      person.name='娟子'
      person.age=16
      // console.log(person);
    }
    return{
      person,
      addSex,
      deleteAge,
      changeInfo
    }
  }
}
</script>

