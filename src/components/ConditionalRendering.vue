<script setup>
import { ref } from 'vue';


const flg = ref(true);

const num = ref(0);
setInterval(() => {
  num.value++;
  console.log(num.value);  //num변수의 내부값 출력헤서 확인하기. num은 블록레벨스코프이므로 브라우저 콘솔에서는 undefind 에러
}, 200);
</script>

<template>
  <!-- 조건부 렌더링 -->
  <!-- true일 경우에만 블록을 렌더링 -->

  <!-- v-show -->
      <!-- false: display: none처리  기본적으로 존재하고 자주 온오프 되는 애 -->
  <button type="button" @click="flg = !flg">온/오프</button>
  <h1 v-show="flg">브이 쇼</h1>  
  
  <!-- v-if( & v-else-if & v-else ) -->
      <!-- false: 아예 요소자체를 없앰.  가끔 나타나는 애 -->
      <!-- if문과 비슷한 형식으로 사용가능(조건문 사용가능) -->
  <h1 v-if="num % 3 === 0" style="color: red;">조건부 렌더링</h1>   
  <h1 v-else-if="num % 2 === 0" style="color: blue;">조건부 렌더링2</h1>   
  <h1 v-else>위의 두 조건 모두 해당 X</h1>
</template>

<style>

</style>