<script setup>
  // Props(프롭스)
      // 부모 컴포넌트에서 자식 컴포넌트로 데이터를 전달하는 사용자 정의 속성
      // 기본 읽기 전용(Readonly), 단방향 데이터 바인딩을 형성
  import { ref } from 'vue';
  import PropsChild from './PropsChild.vue';

  const cnt = ref(0);

  // 2. Component Event 컴포넌트 이밴트:
      // `$emit` 메소드를 사용해서 부모 컴포넌트와 자식 컴포넌트 간 이벤트를 수신&발신
      // 부모가 가진 속성을 "자식쪽에서 변경"하고 싶을 떄
  //  - 부모 컴포넌트는 `v-on`를 사용하여 수신
      // - `@이벤트명="실행할 JS코드"` 자식 컴포넌트 태그 속성으로 추가
  //  - 자식 컴포넌트에서는 `$emit('이벤트명')`으로 발신
      //  아규먼트가 복수일 때는 가변 파라미터로 작성 `$emit('이벤트명'[, ...아규먼트])`
  function minusCnt(num) {
    cnt.value -= num;
  }
</script>

<template>
  <h1>프롭스: {{ cnt }}</h1>

  <!-- 1. 자식 컴포넌트에 ':키명="값"'으로 이루어진 Props'속성'을 부여 -->
  <PropsChild :cnt="cnt" :page="1" @minusCnt="minusCnt"/>
</template>

<style>

</style>