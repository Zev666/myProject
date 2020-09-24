<template>
  <header :style="{ backgroundColor: curMenu.bgColor}">
    <span class="home" @click="goHome">首页</span>
    {{curMenu.name}}
  </header>
</template>

<script>
import { mapState, mapMutations } from "vuex";
export default {
  methods: {
    ...mapMutations(["setCurMenu"]),
    goHome() {
      this.$router.push("/");
      this.setCurMenu({
        path: "/",
        name: "剧集",
        bgColor: "#ff0000",
      });
    },
  },
  computed: {
    ...mapState(["curMenu"]),
  },
};
</script>


<style lang="scss" scoped>
header {
  width: 100%;
  height: 1rem;
  line-height: 1rem;
  text-align: center;
  background: #ff0000;
  position: fixed;
  top: 0;
  left: 0;
  color: #bfa;
  z-index: 999;
  .home {
    position: absolute;
    left: 0;
  }
}
</style>