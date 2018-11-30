<template>
  <div class="header-layout">
    <mynav/>
    <!-- nuxt组件是一个坑，以后凡是使用这个布局组件的页面，他们的组件都会被放进这个坑里面 -->
    <nuxt/>
  </div>
</template>
<script>
import Mynav from '~/components/Mynav'
export default {
  components: {
    Mynav
  }
}
</script>

