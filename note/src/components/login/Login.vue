<template lang="html">
    <div class="container">
        <div class="head">
            <span>用户登录</span>
        </div>
        <Input class='input' v-model="username" placeholder="账号" clearable />
        <Input class='input' v-model="password" placeholder="密码" clearable />
        <Button class="button" type="success" :disabled="submitDisable">提交</Button>
    </div>
</template>
<script>
export default {
    data() {
       return {
           username: '',
           password: '',
           submitDisable: true,
       }
   },
    watch: {
        username: 'userInfoChange',
        password: 'userInfoChange',
    },

    methods: {
        userInfoChange: function() {
            if(this.username && this.password) {
                this.submitDisable = false
            } else {
                this.submitDisable = true
            }
        }
    }

}
</script>

<style lang="css" scoped>
    .container {
        width: 600px;
        height: 400px;
        margin: 0 auto;
        padding: 10px 20px;
    }

    .head {
        font-size:26px;
        margin-bottom: 60px;
    }

    .input {
        display: block;
        width: 280px;
        height: 60px;
        margin: 0 auto;
        margin-bottom: 20px;
    }

    .button {
        width: 280px;
    }
</style>
