<template>
  <div>
    <el-button type="primary" size="default" @click="show = !show"
      >Click Me</el-button
    >
    <el-button type="text" @click="open">打开message box</el-button>
    <div class="content">
      <transition name="el-fade-in-linear">
        <div v-show="show" class="transition-box">el-fade-in-linear</div>
      </transition>
    </div>
    <el-input v-model="number" type="number" step="20" v-focus></el-input>
    <p>{{ animatedNumber }}</p>
    <input v-focus />
  </div>
</template>

<script>
export default {
  name: "FadeInOut",
  data() {
    return {
      show: true,
      number: 0,
      tweenedNumber: 0,
    };
  },
  directives: {
    focus: {
      inserted: function (el) {
        el.focus();
      },
    },
  },
  methods: {
    open() {
      this.$confirm("此操作删除该文件，是否继续？", "提示", {
        confirmButtonText: "确定",
        cancelButtonText: "取消",
        type: "warning",
      })
        .then(() => {
          this.$message({
            type: "success",
            message: "删除成功",
          });
        })
        .catch(() => {
          this.$message({
            type: "info",
            message: "已取消删除",
          });
        });
    },
  },

  computed: {
    animatedNumber() {
      return this.tweenedNumber;
    },
  },

  watch: {
    number(newValue) {
      this.tweenedNumber = newValue;
    },
  },
};
</script>

<style lang="less" scoped>
.content {
  display: flex;
  margin-top: 20px;
  height: 100px;

  .transition-box {
    margin-bottom: 10px;
    width: 200px;
    height: 100px;
    border-radius: 4px;
    background-color: #409eff;
    text-align: center;
    color: #fff;
    padding: 40px 20px;
    margin-right: 20px;
  }
}
</style>
