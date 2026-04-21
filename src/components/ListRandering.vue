<script setup>
import axios from 'axios';
import { reactive, ref } from 'vue';

  const arr = [3, 4, 2, 5];

  // const rea = ref([]);
  const data = reactive([]);

  async function getPicsum() {
    try {
      const url = 'https://picsum.photos/v2/list?page=10&limit=20';
      const res = await axios.get(url);
      data.value = res.data;
    } catch(error) {
      console.log(error);
    }
  }
  getPicsum();
</script>

<template>
  <!-- 리스트 렌더링: v-for -->
  <!-- JS for문과 비슷하게 반복문을 작성-->
  <!-- v-for="배열의값(반복할 대상) in 배열" :key="key명" -->
     <!-- key: Vue가 해당 요소를 식별하게 하기 위한 속성(html의 id & class같은 이름), 스타일 적용 시 사용 -->
  <h1>리스트 렌더링</h1>

<button @click="getPicsum">추가</button>
  <div v-for="value in 5">
    <p>{{ value }}회</p>
  </div>

  <div v-for="(value, key) in arr" :key="key">
    <p>{{ value }}</p>
  </div>

  <div class="container">
    <div class="card" v-for="item in data" :key="item.id">
      <div class="card-img" :style="{backgroundImage: `url('${item.download_url}')`}"></div>
      <span>{{item.id}}: {{ item.author }}</span>
    </div>
  </div>
</template>

<!-- scoped: 자신 이외의 컴포넌트(상위&형제&자식 요소)에 이게 적용되지 않게 함 -->
<style scoped> 
  .container {
    padding: 20px;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 10px;
  }

  .card {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 10px;
  }

  .card-img{
    padding-top: 60%;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
</style>