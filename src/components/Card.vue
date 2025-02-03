<template>
  <div>
    <img :src="oneroom.image" alt="room0" class="room-img">
    <h4 @click="openModal" :style="style1">{{ oneroom.title }}</h4>
    <p> {{ oneroom.price }}</p>
    <!-- <button @click="increase(i)">허위매물 신고</button> <span>신고 수 : {{ count[i] }}</span> -->
  </div>
</template>

<script>

export default {
  name: 'Card',
  data() {
    return {
      style1: 'color:black; cursor: pointer;',
    }
  },
  props: {
    oneroom: Object
  },
  methods : {
    openModal() {
      this.$emit('openModal', this.oneroom.id)
    }
  }
}
</script>

<style></style>