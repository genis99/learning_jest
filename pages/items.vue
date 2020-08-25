<template>
  <div> hello </div>
</template>

<script>
import moment from 'moment'
import CryptoJS from 'crypto-js'
// import axios from 'axios'
// const md5Hash = CryptoJS.MD5('Test')
// const sha256Hash = CryptoJS.SHA256('Test1')
console.log()
// console.log(sha256Hash.toString())
window.open('http://api.smitegame.com/smiteapi.svc/createsessionJson/' + this.devId + '/' + this.signature + '/' + this.now, '_blank')
export default {
  name: 'Items',
  data () {
    return {
      message: 'hola',
      devId: '3465',
      authKey: 'E8FF28B8096047DBBAD36E981D2AD0D4'
    }
  },
  computed: {
    now () {
      return moment().format('YYYYMMDDHHmmss')
    },
    signature () {
      // `this` points to the vm instance
      return CryptoJS.MD5(this.devId + 'createsession' + this.authKey + this.now)
    }
  }
}
</script>

<style scoped>

</style>
