<template>
    <div class="back"  >
      <div class="isleft">
      </div>

        <div class="isright">
          <div >
            <h1 class="login">教 务 系 统 登 录</h1>
            <div class="block">
              <div style="text-align: center">
                <el-form ref="ruleForm" label-width="0px" status-icon>
                  <el-form-item  prop="pass">
                    <el-input type="text" v-model="form.account" autocomplete="off" size="small" placeholder="请输入用户名"></el-input>
                  </el-form-item>
                  <el-form-item  prop="checkPass">
                    <el-input type="password" v-model="form.password" autocomplete="off" size="small" placeholder="请输入密码"></el-input>
                  </el-form-item>
                  <!-- 来个单选框，选择用户登录的身份 -->
                  <el-form-item  prop="checkPass">
                    <el-radio v-model="form.authority" label="1">管理员</el-radio>
                    <el-radio v-model="form.authority" label="2">学生</el-radio>
                    <el-radio v-model="form.authority" label="3">教师</el-radio>
                  </el-form-item>
                  <el-form-item style="margin-bottom: 0;" label-width="0px">
                    <el-button @click="login()" type="primary" size="small" style="width: 120px;background-color: rgb(0,162,214);font-size: 15px">立即登录</el-button>
                  </el-form-item>
                </el-form>
              </div>

            </div>
          </div>

        </div>
    </div>
</template>

<script>
import { login } from '@/api/login/login.js'
import { saveUserLoginToken, saveUserInfo } from '@/utils/storage.js'
export default {
    name: 'LoginView',
    data() {
        return {
            form: {
                password: '',
                account: '',
                authority: '',
            }
        }
    },
    methods: {
        async login() {
            const result = await login(this.form)
            console.log(result)
            if (result.data.code === 1) {
                await this.saveInfo(result.data.data)
                this.$nextTick(()=> {
                    this.$nextTick(()=>{this.$router.push('/home')})
                })
            } else {
                this.$message({
                    type: 'error',
                    message: '账号或密码错误！'
                })
            }
        },
        //存储后端返回的数据
        async saveInfo(data) {
            saveUserLoginToken(data.token)
            saveUserInfo(data)
        }
    }
}
</script>

<style scoped>
    .back {
        background-size: 120%;
        user-select: none;
        position: relative;
        text-align: center;
        width: 100%;
        height: 100vh;
        background-image: url('../../assets/912108(3).png');
        background-repeat: no-repeat;
    }
    /*
    .back > div {
        position: absolute;
        top: 42%;
        left: 50%;
        transform: translate(-50%,-50%);
        width: 40%;
        height: 40%;
        position: fixed;
    }
    */

    .isleft{
      float: left;
      width: 42%;

    }

    /*.logo{
      width: 100%;
      height: 100%;
      background-image: url('../../assets/20210923091943924.webp');
      background-size: auto;

    }*/

    .isright{
      float: right;
      width: 58%;
      height: 100%;
    }

    .login {
        color: aliceblue;
        margin-bottom: 2%;
        margin-top: 17%;
    }


    .block {
        margin:0 auto;
        padding: 4% 10%;
        width: 50%;
        background-color: rgba(255, 255, 255,0.7);
        border-radius: 8px;
        box-shadow: 2px 2px 4px 3px #4d4d4875;
    }
</style>