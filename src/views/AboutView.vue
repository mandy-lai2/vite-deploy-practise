<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ data }}
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
<script>
export default {
  data() {
    return {
      data: {},
    };
  },
  mounted() {
    this.axios.get("https://randomuser.me/api/").then((res) => {
      console.log(res.data);
      this.data = res.data.results[0];
    });
  },
};
</script>
