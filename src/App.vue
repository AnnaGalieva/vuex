<template>
  <div>
    <h2>Counter: {{ count }}</h2>

    <button @click="increment">+</button>
    <button @click="decrement">-</button>
  </div>
  <hr>
  <div>
    <h2>Корзина покупок</h2>
    <ul>
      <li v-for="item in cartItems" :key="item.id">{{ item.name }}-{{ item.price }}</li>
    </ul>
    <p>Общее кол-во товаров в корзине:{{ totalCartItems }}</p>
    <p>Общая стоимость:{{ totalCartPrice }}</p>
    <button @click="addItemToCart({ id: 1, name: 'Товар', price: 10 })">Добавить в корзину</button>
  </div><hr>
  <div>
    <h2>dataFromServer</h2>
    <ul>
      <li v-for="item in data" :key="item">{{ item }}</li>
    </ul>
    <button @click="fetchData">getData</button>
  </div>


</template>

<script>

import { mapState, mapMutations, mapActions, mapGetters } from 'vuex';

export default {
  name: 'App',
  components: {

  },
  computed: {
    ...mapState(['count','data']),
    ...mapGetters(['cartItems', 'totalCartItems', 'totalCartPrice']),

  },
  methods: {
    ...mapMutations(['increment', 'decrement']),
    ...mapActions(['addItemToCart','fetchData'])
  },
}
</script>

<style lang="scss"></style>
