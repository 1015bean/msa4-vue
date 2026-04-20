<script setup>
import { onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUnmounted, onUpdated, ref } from 'vue';

const cnt = ref(0);

// life cycle(생명주기) : 언제 코드 실행할지 알려주는 시스템 => 코드 실행하는 타이밍 문제 해결
    // mount: 컴포넌트가 처음 화면에 랜더링되는 단계
onBeforeMount(() => {
  console.log('onBeforeMount', cnt.value);
});
onMounted(() => {
  cnt.value++;
  console.log('onMounted', cnt.value);
});

    // update: 데이터가 바뀌었을 때 화면이 다시 랜더링되는 단계
onBeforeUpdate(() => {
  console.log('onBeforeUpdate');
})
onUpdated(() => {
  console.log('onUpdated');
})

    // ummount: 컴포넌트가 화면에서 표시되지 않게 되는 단계
onBeforeUnmount(() => {
  console.log('onBeforeUnmount');
})
onUnmounted(() => {
  console.log('onUnmounted');
})
</script>

<template>
  <h1>라이프 사이클: {{ cnt }}</h1>
  <button type="button" @click="cnt++">증가</button>
</template>

<style>

</style>