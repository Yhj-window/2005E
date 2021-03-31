<template>
  <div class="changepage">
    <ul>
      <li v-for="(item, index) in list" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    };
  },
};
</script>

<style lang='scss' scoped>
.changepage {
  ul {
    list-style: none;
    li {
      width: 20px;
      height: 20px;
      text-align: center;
      line-height: 20px;
      border: 1px solid #ccc;
      font-weight: bold;
      float: left;
    }
  }
}
</style>