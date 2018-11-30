<template>
  <section class="container">
    <!-- nuxt-link组件和router-link组件的作用一样，都能用来做路由跳转 -->
    <nuxt-link to="/student">跳转到student页面</nuxt-link>
    <button @click="jumpTo">跳转到student页面</button>
    <!-- 跳转不能直接写a标签，因为a标签相当于重新刷新页面 -->
    <!-- <a href="/student">跳转到student页面</a> -->
    <el-button>测试el-button</el-button>
    <ul>
      <li
        v-for="item in movieList"
        :key="item.id">{{ item.title }}</li>
    </ul>
  </section>
</template>

<script>
  import Logo from '~/components/Logo.vue'
  // import axios from 'axios'
  import axios from '~/plugins/axios'

  export default {
    components: {
      Logo
    },
    data () {
      return {
        movieList: [
          // {title: '肖申克的救赎', id: 1},
          // {title: '大圣归来', id: 2},
          // {title: '当幸福来敲门', id: 3}
        ]
      }
    },
    // 在nuxt中，生命周期函数只有created以及beforeCreate这两个生命周期函数能够在服务端正常使用
    // 在nuxt中发异步请求不能在created生命周期函数中去发，因为它会在前端执行
    // created () {
    //   console.log('created');
    //   setTimeout(() => {
    //     this.movieList = [
    //       {title: '肖申克的救赎', id: 1},
    //       {title: '大圣归来', id: 2},
    //       {title: '当幸福来敲门', id: 3}
    //     ]
    //   }, 1000);
    // },

    // 发送异步请求，在asyncData函数中发送
    // asyncData(context, callback) {
    //   console.log(context);
    //   setTimeout(() => {
    //     // callback有两个参数，第一个是错误对象，第二个是数据对象
    //     callback(null, {
    //       movieList: [
    //         {title: '肖申克的救赎1', id: 1},
    //         {title: '大圣归来1', id: 2},
    //         {title: '当幸福来敲门1', id: 3}
    //       ]
    //     })
    //   }, 1000);
    // },
    // asyncData(context, callback) {
    //   return new Promise((resolve, reject) => {
    //     setTimeout(() => {
    //       resolve({
    //         movieList: [{title: '肖申克的救赎', id: 1},
    //       {title: '大圣归来', id: 2},
    //       {title: '当幸福来敲门', id: 3}]
    //       })
    //     }, 1000);
    //   })
    //     .then(data => {
    //       console.log(data);
    //       callback(null, {movieList: data.movieList})
    //     })
    //     .catch(err => {
    //       callback(err)
    //       context.error(err)
    //     })
    // },
    asyncData(context, callback) {
      axios.get('/coming_soon')
        .then(res => {
          callback(null, {movieList: res.data})
        })
    },
    methods: {
      jumpTo() {
        // this.$router.push({path: '/student'})
        this.$router.push({name: 'student'})
      }
    }
  }
</script>

<style>

</style>
