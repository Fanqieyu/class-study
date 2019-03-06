<template>
  <table cellspacing="0">
    <thead>
      <th v-for="(item,index) in weeks" :key="index">{{item}}</th>
    </thead>
    <tbody>
      <!-- 暂无数据时显示 -->
      <tr v-if="!tableInfo">
        <td :colspan="8">暂无数据</td>
      </tr>
      <!-- template不会被渲染 -->
      <template v-for="item in tableInfo">
        <tr v-for="(wkd,index) in item.workday" :key="index">
          <td>{{wkd.time}}</td>
          <td>{{wkd.monday}}</td>
          <td>{{wkd.tuesday}}</td>
          <td>{{wkd.wednesday}}</td>
          <td>{{wkd.thursday}}</td>
          <td>{{wkd.friday}}</td>
          <!-- v-if控制的是只显示遍历所有中的第一个，不然表格全乱 -->
          <td :rowspan="item.workday.length" v-if="index === 0">{{item.saturday}}</td>
          <td :rowspan="item.workday.length" v-if="index === 0">{{item.sunday}}</td>
        </tr>
      </template>
    </tbody>
  </table>
</template>

<script>
export default {
  data() {
    return {
      weeks: [
        '',
        '周一',
        '周二',
        '周三',
        '周四',
        '周五',
        '周六',
        '周日'
      ],
      tableInfo: [
        {
          saturday: '睡觉',
          sunday: '买菜',
          workday: [
            {
              time: '7:00',
              monday: '做梦',
              tuesday: '起床',
              wednesday: '再睡会儿',
              thursday: '做个美梦',
              friday: '起床'
            },
            {
              time: '9:30',
              monday: '开电脑',
              tuesday: '吃早饭',
              wednesday: '发呆',
              thursday: '看邮件',
              friday: '敲代码'
            },
            {
              time: '12:00',
              monday: '吃午饭',
              tuesday: '切图',
              wednesday: '看手机',
              thursday: '拿饭',
              friday: '吃饭'
            }
          ]
        },
        {
          saturday: '看书',
          sunday: '做饭',
          workday: [
            {
              time: '13:30',
              monday: '',
              tuesday: '',
              wednesday: '',
              thursday: '',
              friday: ''
            },
            {
              time: '18:00',
              monday: '',
              tuesday: '',
              wednesday: '',
              thursday: '',
              friday: ''
            },
            {
              time: '20:00',
              monday: '',
              tuesday: '',
              wednesday: '',
              thursday: '',
              friday: ''
            }
          ]
        },
        {
          saturday: '逛街',
          sunday: '背单词',
          workday: [
            {
              time: '22:30',
              monday: '睡觉',
              tuesday: '洗澡',
              wednesday: '洗澡',
              thursday: '玩手机',
              friday: '综艺'
            }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
  table {
    border: 1px solid #ccc;
  }
  thead th {
    width: 100px;
    text-align: left;
    background-color: #fafafa;
  }
  th,td {
    border: 1px solid #e9eaec;
    padding-left: 10px;
  }
</style>
