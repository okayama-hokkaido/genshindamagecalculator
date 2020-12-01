<template>
  <div>
  <header>
    原神ダメージ計算機
    <p class="text">{{ text }}</p>
    <p class="comment">{{ comment }}</p>

  </header>
    <!-- <Header></Header> -->
    <Form></Form>
  </div>
</template>

<script>
// import Header from './components/Header.vue'
// import Result from './components/Result.vue'
import Form from './components/Form.vue'

export default {
  components: {
    // Header,
    // Result,
    Form
  },
  data(){
    return {
      text: "†この瞬間、おまえは永遠を手にする。†",
      comment: "ダメージを与える敵、キャラクターレベル、元素反応ダメージ、蒸発・融解は順次追加予定"
    }
  }
}
</script>

<style>
header{
  text-align: center;
  background-color: white;
  font-size: 48px;
  font-family: "Meiryo","ヒラギノ角ゴ","sans-serif";
  padding-bottom: 20px;
}
header p{
  font-size: 18px;
  margin:auto;
}
.text{
  color: blue;
  font-weight: bold;
}
body{
  margin: 0;
  background-color: white;
}
div{
  margin: auto;
}
</style>