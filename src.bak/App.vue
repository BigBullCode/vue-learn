<template>
<h3>模板语法</h3>
<p>{{ isMobile }}</p>
<p>{{html}}</p>
<p v-html="html"></p>
</template>

<script>

export default {
  data(){
    return {
      isMobile: false,
      html:"<a href='https://www.baidu.com'>百度</a>"
    }
  }
}
</script>