<template>
  <div class="wrapper">
    <img :src="member.image" :alt="member.firstName" />
    <div class="content">
      <h4>{{ member.firstName }} {{ member.lastName }}</h4>
      <a :href="`https://vuejs.org/v2/guide/`">Member Profile</a>
    </div>
  </div>
</template>
<script>
export default {
  props: ['member'],
};
</script>
<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  padding: 4px;
  text-align: left;
}

.content {
  margin-left: 4px;
}

h4 {
  margin-top: 10px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-weight: bold;
  margin: 0;
}

img {
  border-radius: 50%;
  border: 1px solid #f1f1f1;
}
</style>
