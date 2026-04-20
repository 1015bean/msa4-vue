<script setup>
// 1. 자식 컴포넌트에서는 defineProps()를 이용해 넘어온 데이터 선언
    // 이때 부모 컴포넌트에서 넘겨줄 때 사용한 키를 사용해 선언
    // 데이터 타입도 저장

// defineProps() 작성방법 2가지

// const defineProps = defineProps({
  //   'cnt' : Number,
  //   'page': Number
  // });
  
defineProps(['cnt', 'page']);

// ----------------------------------------------------

// 1. 자식 컴포넌트에서는 defineEmits()를 이용해 넘어온 데이터 선언
//  - 이때 부모 컴포넌트에서 넘겨줄 때 사용한 이벤트명을 사용해 선언
defineEmits(['minusCnt']);
</script>

<template>
  <h1>{{page}}프롭스 자식 컴포넌트: {{ cnt }}</h1>

  <!-- 2. Component Event 컴포넌트 이밴트: -->
    <!-- 자식 컴포넌트에서는 `$emit('이벤트명')`으로 발신 -->
    <!-- 아규먼트가 복수일 때는 가변 파라미터로 작성 `$emit('이벤트명'[, ...아규먼트])` -->
  <button type="button" @click="$emit('minusCnt', 10)">자식 감소</button>
</template>

<style>

</style>