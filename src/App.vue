<template>

  <Modal @closeModal="modal_status = false" :onerooms="onerooms" :user_clicked="user_clicked"
    :modal_status="modal_status" />

  <div class="menu">
    <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
  </div>

  <Discount />

  <Card @openModal="modal_status = true; user_clicked = $event" @increase="warn_count[i]++;" :warn_count="warn_count[i]"
    :oneroom="onerooms[i]" v-for="(a, i) in onerooms" :key="a" />

</template>


<script>
import Card from './components/Card.vue';
import Discount from './components/Discount.vue';
import Modal from './components/Modal.vue';
import data from './assets/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      user_clicked: 0,
      onerooms: data,
      modal_status: false,
      menus: ['Home', 'Shop', 'About'],
      warn_count: [0, 0, 0, 0, 0, 0]
    }
  },
  methods: {

  },

  components: {
    Discount: Discount,
    Modal: Modal,
    Card: Card
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

.detail-img {
  width: 100%;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 78%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.white-bg button {
  cursor: pointer;
}
</style>