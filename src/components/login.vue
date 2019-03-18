<template>
  <div class="container">
    <x-header :right-options="{showMore: true}" :left-options="{showBack: false}">登录</x-header>
    <group title="用户登录">
      <x-input title="手机号" v-model="phone" :max="13"></x-input>
      <x-input title="密码" v-model="password" :max="13"></x-input>
    </group>
    <div class="btn">
      <x-button>登录</x-button>
    </div>
   </div>
</template>

<script>
import { Group, Cell, XHeader, AlertModule, XInput, XButton, Alert } from 'vux'

export default {
  components: {
    Group,
    Cell,
    XHeader,
    AlertModule,
    XInput,
    XButton,
    Alert
  },
  methods: {
    login () {
        if (this.password === '123456'){
              this.$router.push({ path: '/' })
            } else {
              AlertModule.show({
                title: '登录失败',
                content: '密码错误'
              })
          }
      }
  },
  data () {
    return {
      phone: '',
      password: ''
    }
  }
}
</script>

<style>
.btn {
  margin: 10pt
}
</style>