<template>
  <div class="aget">
    <h1>这里是axios的get请求</h1>
    <button @click='getdata'>get方式的无参请求</button>
    <button @click='getdata2'>get方式的带参请求</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  methods: {
    getdata () {
      // 这里是url地址是后台提供的接口
      axios.get('http://localhost:5000/api/v1/index/search')
      //  请求成功之后的回调函数
        .then((res) => {
          console.log(res)
        })
      // 请求失败之后的回调函数
        .catch((err) => {
          console.log(err)
        })
    },
    getdata2 () {
      axios.get('http://127.0.0.1:5000/api/v1/index/get_comment', {
        params: {
          articleId: 8
        }
      })
        .then((res) => {
          console.log(res)
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>

<style>

</style>
