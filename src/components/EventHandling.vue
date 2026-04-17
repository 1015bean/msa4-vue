<script setup>
import { ref } from 'vue';


const cnt = ref(0);

function resetCnt(num) {
  cnt.value = num;
}
</script>

<template>
<!-- 이벤트 핸들링: @이벤트명= "실행할로직" -->
     <!-- : DOM 이벤트를 실행하는 기능 -->
<!-- 인라인 핸들러 & 메소드 핸들러의 2가지 방식이 있다 -->
     <!-- 인라인 핸들러: 이벤트가 실행될 때 ""안에 작성한 코드가 실행됨 -->
     <!-- 메소드 핸들러: 이벤트가 실행될 때 (같은 파일에서 작성한) 함수가 실행됨 -->
     <!-- Vue 메소드 핸들러의 경우, "함수(아규먼트)" 형식으로 사용 가능  -->
<h1>이벤트 핸들링: {{ cnt }}</h1>
<button type="button" @mouseenter="cnt++">인라인 핸들러</button>
<button type="button" @click="resetCnt(5)">메소드 핸들러</button>
</template>

<style>

</style>