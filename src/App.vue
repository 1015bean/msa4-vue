<!-- Vue컴포넌트 작성 양식 -->
    <!-- setup = 컴포넌트를 처리(script의 데이터를 template로 가져오는 기능?)하는 기능을 수행하게 해주는 작성양식 -->

<script setup>
// JS코드 작성 부분
import DataBinding from './components/DataBinding.vue';   //import (불러올 대상) from (불러오는 친구 주소)
import EventHandling from './components/EventHandling.vue'; 
import ConditionalRendering from './components/ConditionalRendering.vue';
import ListRandering from './components/ListRandering.vue';
import Watchers from './components/Watchers.vue';
</script>

<template>
 <!-- HTML코드 작성 부분 -->
   <!-- 작성한 컴포넌트 불러오기 -->
   <DataBinding v-if="false" />
   <EventHandling v-if="false" />
   <ConditionalRendering v-if="false" />
   <ListRandering v-if="false" />
   <Watchers />
</template>

<style>
 /* CSS작성부분 */
</style>