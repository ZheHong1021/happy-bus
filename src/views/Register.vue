<template>
     <div class="register">
      <form action="">
        <h1>註冊介面</h1>

        <div class="input-container">
          <input type="text" id="username" name="username" >
          <span></span>
          <label for="username">Email / 使用者名稱</label>
        </div>
        <div class="input-container">
          <input type="text" id="name" name="name" >
          <span></span>
          <label for="name">名稱</label>
        </div>
        <div class="input-container">
          <input type="password" id="password" name="password" >
          <span></span>
          <label for="password">密碼</label>
        </div>
        <div class="input-container">
          <input type="password" id="confirm_pwd" name="confirm_pwd" >
          <span></span>
          <label for="confirm_pwd">確認密碼</label>
        </div>

        <input type="submit" value="註冊" class="register_btn">
      </form>
  </div>
</template>

<script>
export default {
  name: "Register",

}
</script>

<style lang="scss">
  @import "../assets/scss/form.scss";
</style>