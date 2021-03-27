<script>
import Vue from 'vue';
// Uncomment import and local "components" registration if library is not registered globally.
import { VueFirebaseauthuiFeSample } from '@/entry.esm';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueFirebaseauthuiFeSample,
  },
});
let globalData = new Vue({
  data: {
    $isLogin: true,
    $isEmailVerified: true,
  } 
})
Vue.mixin({
  computed: {
    $isLogin: {
      get: function () { return globalData.$data.$isLogin },
      set: function (newIsLogin) { globalData.$data.$isLogin = newIsLogin; }
    },
    $isEmailVerified: {
      get: function () { return globalData.$data.$isEmailVerified },
      set: function (newIsEmailVerified) { globalData.$data.$isEmailVerified = newIsEmailVerified; }
    },
  }
})
</script>

<template>
  <div id="app">
    <vue-firebaseauthui-fe-sample />
    <VueFirebaseauthuiFeSample />
    <AccountFront />
  </div>
</template>
