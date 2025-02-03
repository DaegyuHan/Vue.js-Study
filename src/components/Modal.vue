<template>
  <div class="black-bg" v-if="modal_status==true">
    <div class="white-bg">
      <h4>{{onerooms[user_clicked].title}}</h4>
      <img class="detail-img" :src="onerooms[user_clicked].image" alt="dd">
      <p>{{onerooms[user_clicked].price}}원</p>
      <p>{{onerooms[user_clicked].content}}</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>

export default {
    name: 'Modal',
    props : {
      onerooms : Array,
      user_clicked : Number,
      modal_status : Boolean
    }
}
</script>

<style>

</style>