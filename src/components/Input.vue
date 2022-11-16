<!--
 * @Date: 2022-11-16 11:52:11
 * @Author: Fancyicookie
-->
<template>
  <div>
    <div>Please enter a binary number</div>
    <div class="alert">{{ alert_info }}</div>
    <input type="text" v-model.trim="binary_num"/>
    <div class="res">{{ decimal_result }}</div>
  </div>
</template>

<script>
export default {
    data() {
      return {
        binary_num: '',
        decimal_result: '',
        alert_info: ''
      }
    },
    methods: {
      convert() {
        this.decimal_result = parseInt(this.binary_num, 2);
        // console.log(this.decimal_result);
      },
      not_binary(nums) {
        if (nums.length == 0) {
          this.decimal_result = ''
        } else {
          for(let i=0; i<nums.length; i++) {
            if (!(nums[i]=='0' | nums[i]=='1')) {
              return false
            } 
          }
        }  
      }
    },
    watch: {
      binary_num(val) {
        val = val.split('')
        if (val.length == 0) {
          this.decimal_result = '';
          this.alert_info = '';
        } else {
          if (this.not_binary(val)==false) {
            this.alert_info = 'please enter 0 or 1';
            this.decimal_result = 'error';
          } else {
            this.alert_info = '';
            this.decimal_result = parseInt(this.binary_num, 2);
          }
        }  
      }
    }
}
</script>

<style>
input {
    margin-bottom: 10px;
    height: 45px;
    width: 310px;
    font-size: 30px;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
.alert {
  margin-bottom: 20px;
  height: 20px;
  font-weight: 700;
  font-size: 24px;
  font-family:'Courier New', Courier, monospace;
  color: rgb(230, 19, 19);
}
.res {
  margin-top: 10px;
  font-size: 36px;
  font-family:'Courier New', Courier, monospace;
  color: rgb(194, 140, 192);
}
</style>