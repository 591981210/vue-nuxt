<template>
  <div class="student">
    <!-- <mynav/> -->
    <h3>这是学生列表页</h3>
    <ul>
      <li
        v-for="item in stuList"
        :key="item.id">
        <nuxt-link :to="`/student/${item.id}`">{{ item.name }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>
<script>
import Mynav from '~/components/Mynav'
export default {
  layout: 'headerlayout',
  components: {
    Mynav
  },
  data () {
    return {
      stuList: [
        {name: 'jack1', id: 1},
        {name: 'jack2', id: 2},
        {name: 'jack3', id: 3}
      ]
    }
  }
}
</script>

