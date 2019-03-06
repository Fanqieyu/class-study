<template>
  <div>
    <table cellspacing="0">
      <thead>
        <th v-for="item in weeks" :key="item">{{item}}</th>
      </thead>
      <tbody>
        <template v-for="(item,index) in tableData">
          <tr :key="index">
            <td>{{item.rowSpanData[0].value01}}</td>
            <td>{{item.rowSpanData[0].value02}}</td>
            <td>{{item.rowSpanData[0].value03}}</td>
            <td>{{item.rowSpanData[0].value04}}</td>
            <td>{{item.rowSpanData[0].value05}}</td>
            <td>{{item.rowSpanData[0].value06}}</td>
            <td>{{item.rowSpanName}}</td>
            <td :rowspan="item.rowSpanData.length">{{item.rowSpanName}}</td>
          </tr>
          <tr v-for="(ele,inx) in item.rowSpanData.length-1" :key="index+'-'+inx">
            <td>{{item.rowSpanData[ele].value01}}</td>
            <td>{{item.rowSpanData[ele].value02}}</td>
            <td>{{item.rowSpanData[ele].value03}}</td>
            <td>{{item.rowSpanData[ele].value04}}</td>
            <td>{{item.rowSpanData[ele].value05}}</td>
            <td>{{item.rowSpanData[ele].value06}}</td>
            <td>{{item.rowSpanData[ele].value07}}</td>
          </tr>
        </template>
      </tbody>
    </table>
  </div>
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
        tableData: [
          {
            rowSpanName: '睡觉',
            rowSpanData: [
              {
                value01: '7:00',
                value02: '再睡5分钟',
                value03: '起床',
                value04: '再睡10分钟',
                value05: '起床',
                value06: '再睡5分钟',
                value07: '睡觉'
              },
              {
                value01: '9:00',
                value02: '再睡5分钟',
                value03: '起床',
                value04: '再睡10分钟',
                value05: '起床',
                value06: '再睡5分钟',
                value07: '睡觉'
              },
              {
                value01: '11:00',
                value02: '再睡5分钟',
                value03: '起床',
                value04: '再睡10分钟',
                value05: '起床',
                value06: '再睡5分钟',
                value07: '睡觉'
              },
            ]
          }
        ]
      }
    }
  }
</script>

<style scoped>
  table {
    /* width: 600px; */
    border: 1px solid #ccc;
  }
  thead th {
    width: 100px;
    text-align: left;
    background-color: #fafafa;
  }
  th,td {
    padding-left: 20px;
    border: 1px solid #e9eaec;
    line-height: 30px;
  }
</style>