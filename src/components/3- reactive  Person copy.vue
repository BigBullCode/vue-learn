
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
    import { reactive } from 'vue';
    //对象数据
    let zhangsan = reactive ({
        name: '张三',
        age: 18
    })
    function chaneAge(){
        zhangsan.age += 1;
    }

    function changePerson(){
        // zhangsan = {name: '李四',age: 20    }
        Object.assign(zhangsan,{name:'李四',age:20})
    }
</script>
    
<style scoped>
.person {
    background-color: aquamarine;
    color: red;
}
</style>