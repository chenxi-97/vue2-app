<template>
  <div>
    <FadeInOut />
    <div>{{ username }}</div>
  </div>
</template>

<script>
import FadeInOut from "@/components/FadeInOut";
export default {
  name: "About",
  components: { FadeInOut },
  computed: {
    username() {
      return this.$route.path;
    },
  },
};
</script>

<style lang="less" scoped></style>
