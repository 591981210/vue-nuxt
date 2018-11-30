<template>
  <section class="container">
    <nuxt-link to="/student">跳转到student页面</nuxt-link>
    <button @click="jumpTo">跳转到 student 页面</button>
    <!--a 标签相当于刷新页面-->
    <!--<a href="/student">跳转到 student 页面</a>-->
    <el-button>测试el-button</el-button>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  methods:{
    jumpTo(){
      // this.$router.push({path:'/student'})
      this.$router.push({name:'student'})
    }
  }
}
</script>

<style>

.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
