<template>
  <div id="app">
    <div class="container">
      <h1 class="title">Ты сегодня покормил кота?</h1>
      <div class="cards">
        <card v-for="(item, index) in items" :key="index"
          :info="item"
        ></card>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./components/Card";

export default {
  name: 'app',
  components: {
    Card
  },
  data () {
    return {
      items: [
        {
          title: 'Нямушка',
          subtitle: 'Сказочное заморское яство',
          consist: 'с фуа-гра',
          amount: '10 порций',
          gift: 'мышь в подарок',
          vol: '0,5',
          descr: 'Печень утки разварная с артишоками.',
          disabled: false,
        },
        {
          title: 'Нямушка',
          subtitle: 'Сказочное заморское яство',
          consist: 'с рыбой',
          amount: '40 порций',
          gift: '2 мыши в подарок',
          vol: '2',
          descr: 'Головы щучьи с чесноком да свежайшая сёмгушка.',
          disabled: false,
        },
        {
          title: 'Нямушка',
          subtitle: 'Сказочное заморское яство',
          consist: 'с курой',
          amount: '100 порций',
          gift: '5 мыши в подарок <br> заказчик доволен',
          vol: '5',
          descr: 'Филе из цыплят с трюфелями в бульоне.',
          disabled: true,
        },
      ]
    }
  }
}
</script>

