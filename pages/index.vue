<template>
  <section class="container">
    <h1 class="title">
      {{ nowdate }}  {{ usrname }}さんの記録
    </h1>
    <div class="usrdata-box">
      <ul>
        <li>身長：{{ usrHeight }}cm</li>
        <li>体重：{{ usrWeight }}kg</li>
        <li>BMI：{{ usrBmi }}</li>
        <li>体脂肪率：{{ usrFat }}%</li>
      </ul>
    </div>
    <div class="usrgraph-box">
    </div>
    <div class="training-box">
      <h2>筋トレメニュー 達成率{{ progress }}%</h2>
      <div class="training-menu">
        <ul v-for="menu in trainingMenu" :key="menu">
          <li><input type='checkbox'>{{ menu }}</li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>

import moment from 'moment'

export default {
  data: ()=>({
    nowdate:moment().format('YYYY年MM月DD日'),
    usrname:'花子',
    trainingMenu:['腕立て','腹筋','筋トレ'],
    progress:0,
    usrHeight:0,
    usrWeight:0,
    usrBmi:0,
    usrFat:0
  }),
  methods: ()=>({

  })
}
</script>

<style>
.container {
  min-height: 100vh;
  display: block;
  text-align: left;
  color: #f08080;
  background-color: #fff5ee;
}

.title-block{
  display: block;
  font-size: 20px;
  text-align: left;
}
</style>

