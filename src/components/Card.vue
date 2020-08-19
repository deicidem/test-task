<template>
  <div class="card" :class="status" @mouseenter="hover = true" @click="onClick($event)" @mouseleave="hover = false">
    <div class="card-content">
      <div class="card-text">
        <div class="card-subtitle" v-if="selected && hover">Котэ не одобряет?</div>
        <div class="card-subtitle" v-else>{{info.subtitle}}</div>
        <h2 class="card-title">{{info.title}}</h2>
        <h3 class="card-title__consist">{{info.consist}}</h3>
        <div class="card-amount">
          {{info.amount}} <br>
          {{info.gift}}
        </div>
      </div>
      <img src="img/Photo.png" alt="" class="card-img">
      <div class="card-vol"> {{info.vol}} <span>кг</span></div>
    </div>
    <div class="card-small" v-show="!info.disabled && !selected">Чего сидишь? Порадуй котэ, <a href="#">купи.</a></div>
    <div class="card-small" v-show="info.disabled">Печалька, {{info.consist}} закончился.</div>
    <div class="card-small" v-show="selected">{{info.descr}}</div>
  </div>
</template>

<script>
export default {
  props: ['info'],
  data() {
    return {
      selected: false,
      hover: false,
    }
  },
  computed: {
    status() {
      if (this.info.disabled) {
        return 'card_disabled'
      } else if (this.selected) {
        if (this.hover) {
          return 'card_active card_active_hover';
        } else {
          return 'card_active'
        }
      } else {
        if (this.hover) {
          return 'card_hover'
        }
      }
    }
  },
  methods: {
    onClick() {
      if (!this.info.disabled) {
        this.selected = !this.selected;
        this.showBlock = true;
        this.hover = false;
      }
    }
  }
}
</script>
