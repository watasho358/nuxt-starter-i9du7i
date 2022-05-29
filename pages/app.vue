<template>
  <div>
    <h2>コンポーネント１</h2>
    <div>
      <input type="text" v-model="value"/>
      <button @click="sample_event">イベント発火</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      value: ""
    }
  },
  methods: {
    sample_event() {
      this.$nuxt.$emit('SAMPLE_EVENT', this.value);
    }
  }
}
</script>