<!--
 * @Date: 2022-11-16 11:52:11
 * @Author: Fancyicookie
-->
<template>
  <div id="app">
    <div class="content">
      <h2>Binary to Decimal Converter</h2>
      <Input></Input>
    </div>
  </div>
</template>

<script>
import Input from './components/Input.vue'

export default {
  name: 'App',
  components: {
    Input
  }
}
</script>

<style lang="less">
#app {   
  background-image:url('./assets/bgc.jpg');
  background-repeat: no-repeat;
  width:100%;
  height:100%;
  position:fixed;
  background-size:100% 100%;
  opacity: 0.8;
  text-align: center;
  color: #c9cdd2;
}
.content{
  width: 500px;
  height: 400px;
  display: flex;
  margin: 80px auto;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  background-color: rgba(0,0,0,0.6);
}
</style>
