<template>
  <div>
    <el-button type="info" @click="logOut">退出</el-button>
  </div>
</template>
<script>
export default {
  methods: {
    logOut () {
      window.sessionStorage.removeItem('token')
      if (window.sessionStorage.getItem('token')) {
        return this.$message({
          showClose: true,
          message: '退出失败',
          type: 'error'
        })
      }
      this.$message({
        showClose: true,
        message: '退出成功',
        type: 'success'
      })
      this.$router.push('/login')
    }
  }
}

</script>
<style lang="less" scoped>

</style>
