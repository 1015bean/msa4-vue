<script setup>
import { ref, Transition } from 'vue';

const flg = ref(false);
</script>

<template>
  <!-- Transition: 애니메이션 효과 넣기 -->
    <!-- 
      템플릿: <Transition name='이름'> 애니메이션 효과 줄 대상 <Transition />
      스타일: (.이름-enter-...{ 스타일 줄 내용 }) (.이름-leave-... { 스타일 줄 내용 }) 
    -->
  <h1>트랜지션</h1>
  <button type="button" @click="flg = !flg">토글</button>
  <Transition name="box">
    <div class="box" v-if="flg"></div>
  </Transition>
</template>

<style>
  .box {
    width: 200px;
    height: 200px;
    background-color: aquamarine;
  }

  /* 등장 애니메이션 */
  .box-enter-from {
    opacity: 0;
  }
  .box-enter-active {
    transition: opacity 1s ease;
  }
  .box-enter-to {
    opacity: 1;
  }

   /* 퇴장 애니메이션 */
  .box-leave-from {
    transform: translateX(0);
  }
  .box-leave-active {
    transition: all 2s;
  }
  .box-leave-to {
    transform: translateX(150vw);
  }
</style>