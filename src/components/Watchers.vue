<script setup>
import { ref, watch } from 'vue';


const email = ref('');
const flgEmail = ref(true);
const flgIsExecuted = ref(false);

// 반응형 속성(데이터바인딩 객체)이 변경될 때마다 감지하고 특정 로직을 실행
// watch(감시대상, 콜백함수[, 옵션])
watch(email, () => {
  if(email.value.includes('@')) {
    flgEmail.value = true;
  } else {
    flgEmail.value = false;
  }
  flgIsExecuted.value = true;
})

// -----------------------------------------------------

const pw = ref('');
const pwClass = ref('');

watch(pw, () => {
  if(pw.value.includes('@')) {
    pwClass.value = 'outline-green';
  } else {
    pwClass.value = 'outline-red';
  }
})

</script>

<template>
  <h1>감시자</h1>
  <div v-if="flgIsExecuted">
    <h1 v-if="flgEmail">O</h1>
    <span v-else>X</span>
  </div>
  <span></span>
  <input type=" text" v-model="email">  <!-- v-model: 양방향 데이터바인딩(templare에서 input받은값을 script의 변수에 할당)-->
<!-- -------------------------------------------------------------------------------- -->
  <input type="text" v-model="pw" :class="pwClass">
</template>

<style>
input {
  outline: none;
}

.outline-green {
  border: 2px solid green;
}

.outline-red {
  border: 2px solid red;
}
</style>