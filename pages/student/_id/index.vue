<template>
  <div class="stu-detail">
    <!-- 这个id对应一个加了下划线的文件夹名 -->
    这是{{ $route.params.id }}号学生的详细信息
  </div>
</template>
<script>
export default {
  // nuxt中使用validate方法进行路由参数校验，这个方法必须返回一个布尔值，为true表示校验通过，为false表示校验失败。注意validate不能写到methods属性中。
  validate(obj) {
    // console.log(obj);
    // return true
    //  只有数字 id
    return /^\d+$/.test(obj.params.id)
  }
}
</script>
