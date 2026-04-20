<!-- 데이터 바인딩 -->
<!-- HTML요소와 state(script에서 작성한 데이터)를 동적으로 연결하는 기능(선언적 렌더링) -->
<!-- const 변수명 = ref||reactive(value); 
     >> 이때 만들어진 변수는 객체 타입(object); 변수값(객체타입이므로 복사해온 주소값)이 바뀌지 않게 하기 위해 const로 변수선언  -->

<script setup>
  import { reactive, ref } from 'vue';   //'vue라이브러리'가 제공하는 툴 'ref'를 불러오기

  // ref( 데이터 )
      // 데이터바인딩 객체1 :object
      // 타입제한 없이 사용할 수 있으나, 
      // 주로 프라이미티므 타입(원시타입)에 반응적 참조(유저의 동작에 대한 반응)를 위해 사용
  const cnt = ref(0);
      // *****ref객체의 경우 js에서 접근 시, 해당 값은 ref.value프로퍼티로 접근*****
  console.log(cnt.value);
// --------------------------------------------------------------------------
  // reactive( 객체 )
      // 데이터바인딩 객체2 :object
      // 객체만 사용 가능하고 , 해당 객체의 반응적 참조를 위해 사용
  const info = reactive({
    name: 'kim',
    age: 20
  });
  console.log(info.name);
// --------------------------------------------------------------------------
  const color = ref('red');

  function btnToggle() {
    if(color.value === 'red') {
      color.value = 'blue';
    }else {
      color.value = 'red';
    }
  }
// -----------------------------------------------------------------------------
  const id = ref('a');
</script>

<template>
   <!-- cnt 객체의 "값"에 접근; ***ref객체는 template에서 객체명 만으로 값에 접근 가능하다*** -->
      <!-- {{ JS데이터(state) }} : JS state를 HTML에 불러오는 문법 -->
   <!-- 이벤트핸들러 [ @이벤트 효과 = '코드' ] : 이벤트 발생 시 실행할 로직을 연결하는 문법 -->
   <h1>데이터 바인딩 {{ cnt }}</h1>
   <button type="button" @click="cnt++">증가</button>
   <button type="button" @click="cnt--">감소</button>

   <!-- info 객체 및 그 속성값에 접근 -->
   <h3>{{ `${info.name} : ${info.age}` }}</h3>

   <!-- v-bind: 속성값에 데이터 바인딩 객체를 사용 -->
      <!-- ":" "HTML태그의 속성(html태그안에 들어가는 친구들)" = "js데이터(변수, 함수)" -->
   <h3 class="test" :class="color">태그 속성값 데이터 바인딩</h3>
   <button type="button" @click="btnToggle">색깔 토글</button>

   <!-- 양방향 데이터바인딩: HTML에서 js데이터에 영향을 줌 -->
       <!-- v-model 사용 -->
   <input type="text" v-model="id">
   <p>{{ id }}</p>
</template>

<style>
.red {
  color: red;
}
.blue {
  color: blue;
}
.test {
  background-color: beige;
}
</style>