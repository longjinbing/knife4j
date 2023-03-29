<template>
  <a-layout-content class="knife4j-body-content">
    <a-row :gutter="24">
      <a-col :span="8" v-for="param in swaggerCurrentInstance.pathArrs" :key="param.method" >
      <a-card :size="small">
        <h3 class="card-title"><span>{{param.method}}</span></h3>
        <p class="cart-num-title">数量<span class="cart-num">{{param.count}}</span></p>
      </a-card>
      </a-col>
    </a-row>
  </a-layout-content>
</template>
<script>
export default {
  props: {
    data: {
      type: Object
    }
  },
  components: {
    "Markdown": () => import('@/components/Markdown')
  },
  computed: {
    swaggerCurrentInstance() {
      return this.$store.state.globals.swaggerCurrentInstance;
    },
    settings() {
      return this.$store.state.globals.settings;
    }

  },
  data() {
    return {
      title: "knife4j"
    };
  },
  created() {
    // console.log(this.settings);
    // console("子组件渲染");
    // console(this.data);
  }
};
</script>
<style scoped>
.content-line {
  height: 25px;
  line-height: 25px;
}

.content-line-count {
  height: 35px;
  line-height: 35px;
}

.title {
  text-align: center;
  width: 80%;
  margin: 5px auto;
}

.description {
  width: 90%;
  margin: 15px auto;
}

.divider {
  margin: 4px 0;
}

.divider-count {
  margin: 8px 0;
}
.knife4j-body-content{
  padding:24px;
  background-color: rgb(240, 242, 245);
}
.card-title{
  line-height: 40px;
}

.cart-num{
  color: #61affe;
  font-size:30px;
  padding-left: 50px;
}
.cart-num-title{
  vertical-align: middle;
}
</style>
