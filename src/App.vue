<template>
  <div class="container" id="app">
    <h1>{{ $route.meta.title }}</h1>
    <button
      v-if="$route.name != 'index'"
      class="contrast"
      style="display: inline-block; width: auto"
      type="button"
      @click="() => $router.go(-1)">
      返回上级
    </button>
    <keep-alive v-if="$route.meta.keepAlive">
      <router-view :key="$route.fullPath"> </router-view>
    </keep-alive>
    <router-view v-else :key="$router.fullPath">
      <!-- 这里是不被缓存的视图组件，比如 page3 -->
    </router-view>
    <div><strong>这是公共Footer</strong></div>
  </div>
</template>
<script>
export default {};
</script>
