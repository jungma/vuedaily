<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>{{  seen ? 'yes' : 'no'}}</p>
    <p v-if="seen">이제 나를 볼 수 있어요</p>
    <p v-else>이제 나를 볼 수 없어요2</p>
    <!-- <p v-else-if="neverSeen">이제 나를 볼 수 없어요</p> -->
    <p v-show="seen">이제 나를 볼 수 있어요</p>
    <p v-show="!seen">이제 나를 볼 수 없어요</p>

    <!-- 

    1. v-if & v-show 차이점
    v-if : display:none; css 로 제어
    v-show : 태그 자체를 show hide 

    -->
    <a :href="url">링크 이동 </a>
    <img :src="imagePath" />

    <!-- 2. v-bind:class -->
    <div :class="{ active : isActive }">활성화</div>

    <!-- 3. v-bind:style -->
    <div :style="{ color: activeColor, fontSize: fontSize + 'px' }">스타일정의</div>

    <!-- 4. v-for : vue 2.2.0 이상에서 key값은 필수 -->
    <ul>
      <li v-for="item in items" :key="item.name">
        {{item.name}} - {{ item.age }}
      </li>
    </ul>
    <ul>
      <li v-for="(key, val, index) in person" :key="index">
        {{index}}  {{key}} {{val}}
      </li>
    </ul>
  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  // props: {
  //   msg: String
  // },
  data(){
    return {
      msg:'ㅂㄱ',
      seen : true,
      url : 'http://google.com',
      isActive:true,
      activeColor:'red',
      fontSize:12,
      imagePath:'/assets/logo.png',
      items:[
        {name:'red', age: 15},
        {name:'blue', age: 25},
        {name:'greed', age: 35},
      ],
      person:{
        name:'mingo',
        age : 34,
        location : 'incheon'
      }

      
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
