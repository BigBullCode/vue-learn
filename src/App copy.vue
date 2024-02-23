<!-- .vue文件中要写三种标签,分别为 template  script style三种标签 -->

<template>
<div class="app">
    <h1>你好!!!</h1>
    <Person/>
</div>
</template>

<script lang="ts">
import Person from './components/Person.vue'
//js或ts
export default {
    name: 'App',  //组件名
    components: {
        Person
    },//注册组件
    
}
</script>

<style>
.app {
    background-color: blue;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}
</style>