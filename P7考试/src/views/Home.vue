<template>
  <div class="home">
    <input
      type="text"
      class="search"
      @input="search"
      placeholder="商品名称"
      v-model="value"
    />
    <div>
      <div>
        <span class="span">编号 <icon class="icon"></icon> </span>
        <span class="span">名称</span>
        <span class="span">价格 <icon class="icon"></icon></span>
      </div>
      <table cellspacing="0">
        <tr v-for="item in list" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.goods_name }}</td>
          <td>{{ item.price }}</td>
        </tr>
      </table>
      <p>
        每页<input type="text" class="list" value="10" /><span class="up"
          >^</span
        ><span class="down">^</span> 条，共 10 条
      </p>
      <change-page class="page"></change-page>
    </div>
  </div>
</template>

<script>
import icon from "@/components/icon.vue";
import changePage from "@/components/changePage.vue";
export default {
  name: "Home",
  components: {
    icon,
    changePage,
  },
  data() {
    return {
      list: [],
      value:'',
    };
  },
  mounted() {
    console.log(this);
    this.$axios({
      url: "data.json",
    }).then((res) => {
      console.log(res.data.data);
      this.list = res.data.data;
    });
  },
  methods: {
    search() {
      console.log(this.value);
      this.list.filter((item)=>{
          return 
      })
    },
  },
};
</script>
<style lang="scss" scoped>
.home {
  .search {
    // margin-left: 20px;
  }
  div {
    width: 100%;
    margin: 10px auto;
    background-color: #ececec;
    .span {
      display: inline-block;
      width: 33%;
      height: 40px;
      line-height: 40px;
      background-color: #ececec;
      text-align: center;
      font-weight: bold;
      font-size: 20px;
      .icon {
        width: 32px;
        height: 32px;
        margin: -36px 0 0 330px;
      }
    }
    table {
      width: 100%;
    }
    tr,
    td {
      border: 1px solid gray;
      width: 33%;
    }
    .list {
      outline: springgreen;
      width: 60px;
    }
    p {
      position: relative;
      .up {
        display: inline-block;
        position: absolute;
        top: 3px;
        left: 77px;
      }
      .down {
        display: inline-block;
        position: absolute;
        top: 5px;
        left: 77px;
        transform: rotate(180deg);
      }
    }
    .page {
      margin-left: 1604px;
    }
  }
}
</style>