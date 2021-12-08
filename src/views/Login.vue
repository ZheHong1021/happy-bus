<template>
     <div class="login">

      <form @submit.prevent="handleSubmit" method="POST">
       <h1>登入介面</h1>
        <div class="input-container">
          <input type="text" id="username" name="username" v-model="form_data.username">
          <span></span>
          <label for="username">Email / 使用者名稱</label>
        </div>
        <div class="input-container">
          <input type="password" name="password" id="password" v-model="form_data.password">
          <span></span>
          <label for="password">密碼</label>
        </div>

        <input type="submit" value="登入" class="login_btn">
      </form>
  </div>
</template>

<script>
import { reactive } from '@vue/reactivity'
export default {
    name: "Login",

    setup(){
      const form_data = reactive({
        username: '',
        password: '',
      });

      const handleSubmit = ()=>{
        console.log(form_data);
      }

      return {form_data, handleSubmit}
    }
}
</script>

<style lang="scss">
  @import "../assets/scss/form.scss";
</style>