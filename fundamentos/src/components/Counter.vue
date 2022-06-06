<template>
  <div>
    <h2>{{ customTitle }}</h2>
    <p>{{ count }} <sup>2</sup> = {{ getSquareCounter }}</p>
    <button @click="incrementar">+1</button>
    <button @click="decrementar">-1</button>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Counter'
    },
    inicio: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      count: this.inicio,
    };
  },
  methods: {
    getSquare() {
      return this.count * this.count;
    },
    incrementar() {
      this.count++;
    },
    decrementar() {
      this.count--;
    },
  },
  computed: {
    getSquareCounter() {
      return this.count * this.count;
    },
    customTitle() {
      return this.title + ": " + this.count;
    },
  },
};
</script>

<style>
</style>