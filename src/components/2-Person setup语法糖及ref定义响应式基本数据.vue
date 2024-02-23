<!-- .vue文件中要写三种标签,分别为 template  script style三种标签 -->

<template>
    <div class="person">
        <h1>姓名:{{ name }}</h1>
        <h1>年龄:{{ age }}</h1>
        <h1>
            <button @click="showContent">点击查看保密信息</button>
        </h1>
        <button @click="changeAge">修改年龄</button>
    </div>
</template>
<script lang="ts">
    export default {
        // vue3为组合式风格,使用组合式api
        name: 'Person',
        // setup() {
        //     //数据,这里写死的,无法修改,非响应式/ 原因:setup函数会在beforeCreate之前调用,它是领先所有钩子执行的.
        //     // 尽管setup先修改了数据,但是vue执行后依然没有变
        //     let name = '张三';
        //     let age = 18;
        //     let tel = 1234566;

        //     //方法
        //     function showContent() {
        //         alert('姓名:' + name + '年龄:' + age + '电话:' + tel)
        //     }
        //     return {
        //         name,
        //         age,
        //         showContent
        //     }
        // }
    }
</script>

<!-- setup语法糖 -->
<script setup lang="ts">
//表示一个setup函数
// setup语法糖
// setup语法糖,相当于setup函数中的data()方法
// setup语法糖,相当于setup函数中的methods方法
// setup语法糖,相当于setup函数中的computed方法
// setup语法糖,相当于setup函数中的watch方法
// setup语法糖,相当于setup函数中的mounted钩子函数
// setup语法糖,相当于setup函数中的created钩子函数

//声明数据为响应式数据

    import { ref } from 'vue'

    //同时表示声明及发布,无需再次输出
    let name = '张三';
    let age = ref(18);
    let tel = 1234566;

    //方法
    function showContent() {
        alert('姓名:' + name + '年龄:' + age.value + '电话:' + tel)
    }
    function changeAge() {
        age.value += 1;
    }   
</script>
    
<style scoped>
.person {
    background-color: aquamarine;
    color: red;
}
</style>