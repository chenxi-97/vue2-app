<template>
  <div class="home">
    <HelloWorld name="test" />
  </div>
</template>

<script>
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

export default {
  name: "Home",
  components: { HelloWorld },
};
</script>

<style lang="less" scoped></style>
