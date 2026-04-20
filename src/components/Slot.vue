<script setup>
// 템플릿 컨텐츠를 부모 컴포넌트에서 자식 컴포넌트에 전달
//  - 부모 컴포넌트에서 <SlotChild>자식에게 보내줄 요소</SlotChild> 작성
//  - 자식 컴포넌트는 출력하고 싶은 위치에 <slot>태그를 작성

import { ref } from 'vue';
import SlotChild from './SlotChild.vue';

const cnt = ref(0);
</script>

<template>
  <h1>슬롯</h1>
  <SlotChild>
    <button type="button" @click="cnt +=2">버튼</button>
    <h2>자식이에게 보내줄 슬롯 : {{ cnt }}</h2>
  </SlotChild>
</template>

<style>

</style>