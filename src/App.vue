<template>
  <div id="app">
    <el-row type="flex" justify="center"> 
      <el-col :span="8">
        <el-tabs v-model="active_form">
          <el-tab-pane name="login">
            <el-form :model="login" label-position="right" label-width="80px">
              <el-form-item label="用户名">
                <el-input v-model="login.username" placeholder="用户名"></el-input>
              </el-form-item>
              <el-form-item label="密码">
                <el-input v-model="login.password" placeholder="密码"></el-input>
              </el-form-item>
              <el-button type="primary">登录</el-button>
            </el-form>
          </el-tab-pane>
          <el-tab-pane name="sign">
            <el-form :model="sign_up" label-position="right" label-width="80px">
              <el-form-item label="用户名">
                <el-input v-model="sign_up.username" placeholder="用户名"></el-input>
              </el-form-item>
               <el-form-item label="昵称">
                <el-input v-model="sign_up.nickname" placeholder="昵称"></el-input>
              </el-form-item>
              <el-form-item label="密码">
                <el-input v-model="sign_up.password" placeholder="密码" type="password"></el-input>
              </el-form-item>
              <el-form-item label="确认密码">
                <el-input v-model="sign_up.confirm_password" placeholder="确认密码" type="password"></el-input>
              </el-form-item>
              <el-button type="success">注册</el-button>
            </el-form>
          </el-tab-pane>
        </el-tabs>
        <div class="change" style="text-align:center">
          <span @click="change">{{ operation }}</span>
        </div>
      </el-col>
    </el-row>
    <el-row>
      
    </el-row>
  </div>
</template>

<script>

export default {
  name: 'app',
  data(){
    return{
      active_form: 'login',
      operation: '注册',
      login:{
        username: '',
        password: ''
      },
      sign_up:{
        username: '',
        nickname: '',
        password: '',
        confirm_password: '',
      }
    }
  },
  methods:{
    change(){
      (this.active_form == 'login')?this.active_form = 'sign':this.active_form = 'login';
      (this.operation == '登录')?this.operation = '注册':this.operation = '登录';
    }
  }
}
</script>

<style>

</style>
