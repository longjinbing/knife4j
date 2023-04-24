<template>
  <a-layout-content class="knife4j-body-content">
    <a-card :size="small" title="接口数量">
      <a-row :gutter="24">
        <a-col :span="6" v-for="param in swaggerCurrentInstance.pathArrs" :key="param.method" >
          <div class="card-content">
            <div class="card-content-method">{{param.method}}</div>
            <div class="card-content-method-num">{{param.count}}</div>
          </div>
        </a-col>
      </a-row>
    </a-card>
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
.card-title{
  line-height: 40px;
}

.card-content{
  text-align: center;
  margin:30px auto 40px auto;
}
.card-content-method{
  font-size:16px;
  text-align: center;
  margin: 20px auto;
  font-weight: 600;
  width: 80px;
  line-height: 30px;
  height:30px;
  cursor:pointer
}
.card-content-method-num{
  font-size:30px;
  line-height: 100px;
  width: 100px;
  height:100px;
  border-radius: 50px;
  background-color: #025cbd;
  color: #fff;
  margin: auto;
  cursor:pointer
}
</style>
