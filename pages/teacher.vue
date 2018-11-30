<template>
  <div class="teacher">
    <!-- <mynav/> -->
    <h3>这是教师列表页</h3>
    <ul>
      <li
        v-for="item in teacherList"
        :key="item.id">
        <nuxt-link :to="`/teacher/${item.id}`">{{ item.name }}</nuxt-link>
      </li>
    </ul>
    <!-- nuxt-child组件用来存放嵌套的组件 -->
    <nuxt-child/>
  </div>
</template>
<script>
import Mynav from '~/components/Mynav'
export default {
  // 通过layout属性，指定当前页面使用的布局组件
  layout: 'headerlayout',
  components: {
    Mynav
  },
  data () {
    return {
      teacherList: [
        {name: 'jack1', id: 1},
        {name: 'jack2', id: 2},
        {name: 'jack3', id: 3}
      ]
    }
  }
}
</script>

