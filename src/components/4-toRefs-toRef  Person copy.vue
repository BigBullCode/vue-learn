
<template>
    <div class="person">
       <h2>姓名:{{zhangsan.name}}</h2>
       <h2>年龄:{{zhangsan.age}}</h2>
       <button @click="chaneAge">修改年龄</button>
    </div>
</template>
<script lang="ts">
    export default {
        
        name: 'Person',
       
    }
</script>

<!-- setup语法糖 -->
<script setup lang="ts">
    import { reactive, toRefs, toRef} from 'vue';
    //对象数据
    let zhangsan = reactive ({
        name: '张三',
        age: 18
    })

    //这种解构出来的变量全部都是非响应式变量,无法修改
    // let {name, age} = zhangsan
    // function chaneAge(){
    //     //无法修改
    //     age += 1;
    // }
    //toRefs深度定义响应式解构
    let {name, age} = toRefs(zhangsan)
    function chaneAge(){
        //可以修改
        age.value += 1;
    }

    let aage = toRef(zhangsan, 'age')




</script>
    
<style scoped>
.person {
    background-color: aquamarine;
    color: red;
}
</style>