<template>
  <div>
    <h2>コンポーネント２</h2>
    <div>
      <span v-text="data"></span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: null
    }
  },
  created() {
    this.$nuxt.$on('SAMPLE_EVENT', data => {
      this.data = data;
    });
  },
  beforeDestroy() {
    this.$nuxt.$off('SAMPLE_EVENT');
  }
}
</script>