<template>
  <div>
    <img :src="oneroom.image" alt="room0" class="room-img">
    <h4 @click="openModal" :style="style1">{{ oneroom.title }}</h4>
    <p> {{ oneroom.price }}</p>
    <button class="warn-bt" @click="increase">허위매물 신고</button> <span>신고 수 : {{ warn_count }}</span>
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
    oneroom: Object,
    warn_count: Number
  },
  methods : {
    openModal() {
      this.$emit('openModal', this.oneroom.id)
    },
    increase() {
      this.$emit('increase')
    }
  }
}
</script>

<style>
.warn-bt {
  cursor: pointer;
}
</style>