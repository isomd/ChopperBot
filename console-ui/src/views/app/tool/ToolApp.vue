
<script>
import ToolMenu from "./component/ToolMenu";
export default {
  name: "ToolApp.vue",
  components: {ToolMenu}
}
</script>
<template>
  <div class="app-container">
    <div class="d-none d-md-block sidebar">
      <ToolMenu></ToolMenu>
    </div>

    <div class="main">
      <router-view v-slot="{ Component }">
        <transition name="fade">
          <component :is="Component" />
        </transition>
      </router-view>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.app-container {
  display: flex;
  height: calc(100vh - 240px);
  width: 100%;
  font-size: 13px;
  padding: 20px;

  .sidebar {
    display: flex;
    flex-direction: column;
    width: 300px;
    height: 100%;
    background-color: #fff;
    margin-right: 20px;
  }

  .main {
    flex: 1;
    width: 100%;
    height: 100%;
    background-color: #fff;
  }
}
</style>
