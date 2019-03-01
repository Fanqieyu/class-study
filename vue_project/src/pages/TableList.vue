<template>
  <div class="tablestyle">
    <table>
      <thead>
        <tr>
          <th v-for="week in weeks">{{week.text}}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="time in data">
          <td v-for="i in time.day">{{i}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        weeks: [
          {text: ''},
          {text: '周一'},
          {text: '周二'},
          {text: '周三'},
          {text: '周四'},
          {text: '周五'},
          {text: '周六'},
          {text: '周日'}
        ],
        data:[
          {day:['7:00','睡觉','起床',3,5,'再睡',4,7]},
          {day:['9:30',1,8,'吃早餐',3,5,4,7]},
          {day:['12:00',1,8,17,3,'吃午饭',4,7]},
          {day:['13:30','午休',8,17,3,5,4,7]},
          {day:['18:00',1,8,17,3,5,4,7]},
          {day:['19:00',1,8,17,3,5,4,7]},
          {day:['22:00',1,8,17,3,5,4,7]},
        ]
      }
    }
  }
</script>

<style lang="less" scoped>
  .tablestyle {
    margin: 10px;
    .table {
      padding: 2px;
    }
  }
</style>


