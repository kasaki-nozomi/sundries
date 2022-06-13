<template>
  <div>
    <el-card class="card">Jashin</el-card>
  </div>
</template>

<script>

export default({
  setup() {
      // commit one
  },
})
</script>


<style lang="scss" scoped>
.card {
  height: 100px;
}
.el-card {
  background: palegreen;
}
:deep(.el-card__body) {
    color: pink;
}
</style>
