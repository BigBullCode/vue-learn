<!-- .vue文件中要写三种标签,分别为 template  script style三种标签 -->

<template>  
    <Person/>
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
