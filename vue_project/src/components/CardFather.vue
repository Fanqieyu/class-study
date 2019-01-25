<template>
  <div class="cardfather">
    <div>
      <button class="btncard" @click="add">增加卡片</button>
    </div>
    <card-add :last="last" :now="now"></card-add>
    <div>
      <card v-for="item in cards" :key="item.value" :card="item" @cardcolor="cardcolor"></card>
    </div>
  </div>
</template>

<script>
  import card from './card.vue'
  import CardAdd from './CardAdd.vue'
  export default {
    name: '',
    components: {
      card,
      CardAdd
    },
    data() {
      return {
        cards: [],
        last: 0,
        now: 0
      }
    },
    methods: {
      add() {
        this.cards.push({
          index: this.cards.length + 1,
          status: ''
        })
      },
      cardcolor(it) {
        this.last = this.now;
        this.now = it.index;
        this.cards.forEach((item) => {
          item.status="";
          if(item.index == this.last) {
            item.status = 'last'
          }
          if(item.index == this.now) {
            item.status = 'now'
          }
        })
      }
    }
  }
</script>

<style scoped>
  .btncard {
    width: 200px;
    height: 40px;
    border-radius: 10px;
    outline: none;
    background-color: #8ab7e4;
    color: white;
    font-size: 20px;
    border-width: 0;
  }
</style>
