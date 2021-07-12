<script>
// 在store/index.js定義了state, 使用useStore方法來取得state
import { useStore } from "vuex";

export default {
  setup() {
    const store = useStore();

    const handClickMenu = () => {};

    return { handClickMenu };
  }
};
</script>
<template>
  <a class="menuBtn" @click="handClickMenu">
    <i class="fas fa-bars fa-3x"></i>
  </a>
</template>
<style lang="scss" scoped>
a.menuBtn {
  cursor: pointer;
  position: absolute;
  color: #fff;
  z-index: 10;
  top: 50px;
  right: 50px;
}
</style>
