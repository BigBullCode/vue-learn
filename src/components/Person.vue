
<template>
    <div class="person">
       姓:<input type="text" v-model="firstName"> <br>
       名:<input type="text" v-model="lastName"> <br>
       全名:<input type="text" v-model="fullname"> <br>
       全名:<span>{{fullname}}</span> <br>
    </div>
</template>
<script lang="ts">
    export default {
        name: 'Person',
    }
</script>

<!-- setup语法糖 -->
<script setup lang="ts">
   import { ref , computed} from 'vue';

   let firstName = ref('张')
   let lastName = ref('三')

   let fullname = computed({
    get(){
        return firstName.value+ '-' + lastName.value
    },
    set(val) {
        const [str1, str2] = val.split('-')
        firstName.value = str1
        lastName.value = str2
    }
   })

</script>
    
<style scoped>
.person {
    background-color: aquamarine;
    color: red;
}
</style>