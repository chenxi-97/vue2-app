<template>
  <div>
    <div class="title">{{ reverseName }}</div>
    <el-button style="padding: 8px 10px" size="small" type="danger"
      >确认</el-button
    >
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    name: {
      type: String,
      default: "",
    },
  },

  data() {
    return {
      title: "",
    };
  },

  mounted() {
    window.addEventListener("resize", this.handleResize);
  },

  beforeDestroy() {
    window.removeEventListener("resize", this.handleResize);
  },

  methods: {
    handleResize() {
      console.log(window.Vue);
      console.log(123);
    },
  },

  computed: {
    reverseName: function () {
      return this.name + 123;
    },
  },
};
</script>

<style lang="less" scoped>
.title {
  color: red;
  font-size: 20px;
}
</style>
