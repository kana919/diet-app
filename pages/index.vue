<template>
  <section class="container">
    <div class="title-box">
      <h1 class="title">
        {{ nowdate }}  {{ usrname }}さんの記録
      </h1>
    </div>
    <div class="usrdata-box">
      <h2></h2>
      <ul>
        <li>身長：{{ usrHeight }}cm</li>
        <li>体重：{{ usrWeight }}kg</li>
        <li>BMI：{{ usrBmi }}</li>
        <li>体脂肪率：{{ usrFat }}%</li>
      </ul>
    </div>
    <img class="siba-illust" src="~assets/image/siba-taijukei.png"  alt="柴犬">
    <div class="graph-box">
      <BarChart />
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
import BarChart from '@/components/BarChart.vue'

export default {
  data: ()=>({
    nowdate:moment().format('YYYY年MM月DD日'),
    usrname:'花子',
    trainingMenu:['腕立て','腹筋','筋トレ'],
    progress:0,
    usrHeight:0,
    usrWeight:0,
    usrBmi:0,
    usrFat:0,     
  }),
  components: {
    BarChart
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  min-width: 400px;
  display: block;
  text-align: left;
  color: #f08080;
  background-color: #fff5ee;
  border: 35px solid transparent;
}

.container ul{
  list-style: none;
  padding: 0px;
}

/**********************************/
/*          　 タイトル             */
/**********************************/

.title-box{
  display: block;
  width: inherit;
  height: 100px;
  background-image: url('~assets/image/title.png');
  background-repeat: no-repeat;
  background-position: center center;
}

.title{
  text-align: center;
  width: inherit;
  line-height: 3.5em;
}

/**********************************/
/*         ユーザーデータ           */
/**********************************/

.usrdata-box{
  display: inline-block;
  width: 25%;
  font-size: 20px;
  margin: 5px;
  padding: 10px;
  border: 4px solid #000000;
  border-radius: 15px;
  background-color: #ffffff;
}

.usrdata-box li{
  padding-left: 28px;
	line-height: 1.6em;
  background: url('~assets/image/list-illust1.png') left 0px top 2px no-repeat;
  background-size: 28px auto;
}

/**********************************/
/*         イラスト配置             */
/**********************************/
.siba-illust{
  position: relative;
  bottom: -30px;
  left: -15px;
}


/**********************************/
/*         グラフデータ         　  */
/**********************************/
.graph-box{
  display: inline-block;
  width: 35%;
  font-size: 20px;
  margin: 5px;
  margin-left: 10px;
  padding: 10px;
  border: 4px solid #000000;
  border-radius: 15px;
  background-color: #ffffff;
}

/**********************************/
/*         筋トレメニュー           */
/**********************************/
.training-box{
  display: block;
  font-size: 20px;
  margin: 5px;
  padding: 10px;
  border: 4px solid #000000;
  border-radius: 15px;
  background-color: #ffffff;
}


</style>

