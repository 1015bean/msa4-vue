<!-- Vue컴포넌트 작성 양식 -->
    <!-- setup = 컴포넌트를 처리(script의 데이터를 template로 가져오는 기능?)하는 기능을 수행하게 해주는 작성양식 -->

<script setup>
// JS코드 작성 부분
import DataBinding from './components/DataBinding.vue';   //import (불러올 대상) from (불러오는 친구 주소)
import EventHandling from './components/EventHandling.vue'; 
import ConditionalRendering from './components/ConditionalRendering.vue';
import ListRandering from './components/ListRandering.vue';
import Watchers from './components/Watchers.vue';
import Props from './components/Props.vue';
import Slot from './components/Slot.vue';
import MyTransition from './components/MyTransition.vue';
import LifeCycle from './components/LifeCycle.vue';
import { ref } from 'vue';

const flgLifeCycle = ref(true);
</script>

<template>
 <!-- HTML코드 작성 부분 -->
   <!-- 작성한 컴포넌트 불러오기 -->
   <DataBinding v-if="false" />
   <EventHandling v-if="false" />
   <ConditionalRendering v-if="false" />
   <ListRandering v-if="false" />
   <Watchers v-if="false"/>
   <Props v-if="false"/>
   <Slot v-if="false"/>
   <MyTransition v-if="false"/>
   <LifeCycle v-if="flgLifeCycle"/>

   <button type="button" @click="flgLifeCycle = !flgLifeCycle">라이프사이클 컴포넌트 토글</button>
</template>

<style scoped>   
      /* scoped: 자신 이외의 컴포넌트(상위&형제&자식 요소)에 이게 적용되지 않게 함 */
 /* CSS작성부분 */
</style>