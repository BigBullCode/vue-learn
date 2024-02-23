<!-- .vue文件中要写三种标签,分别为 template  script style三种标签 -->

<template>
    <div class="person">
        <h1>{{msg}}</h1>
        <h1>
            <button @click="showContent">点击查看保密信息</button>
        </h1>
    </div>
</template>
    <script lang="ts">
    export default {
// 配置项API,后续都是配置项, 为vue2.0的技术类型.  vue3为组合式风格,使用组合式api
        name: 'Person',
        data() {
            return {
                msg: 'Hello World!',
                content:'保密信息:你好!!!'
            }
        },
        methods:{
            showContent(){
                alert(this.content)
            }
        }
    }
</script>
    
<style scoped>
    .person {
        background-color: aquamarine;
        color: red;
    }   
</style>