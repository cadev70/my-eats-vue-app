<template>
  <div>
    <b-sidebar
      id="sidebar-backdrop"
      title="Sidebar with backdrop"
      backdrop-variant="dark"
      backdrop
      shadow
      no-header
    >
      <div class="px-3 py-2">
        <b-button class="w-100">登入</b-button>
        <div class="guide mt-5">
          <p>新增企業帳號</p>
          <p>新增您的餐廳</p>
          <p>註冊成為合作外送夥伴</p>
        </div>
      </div>
    </b-sidebar>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.guide {
  text-align: left;
}
</style>
