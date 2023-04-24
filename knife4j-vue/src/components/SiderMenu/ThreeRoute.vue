<template>
  <router-link
    :class="{
            'knife4j-menu-api-deprecated':item.deprecated,
            [item.menuClass]:true
          }"
    :to="item.path"
  >
    <my-icon v-if="item.icon" :type="item.icon"></my-icon>
    <a-badge v-if="enableVersion&&item.hasNew" status="processing" title="新接口" style="margin-bottom:3px;" />
    <a-tag v-if="item.method === 'GET'" color="green">{{item.method}}</a-tag>
    <a-tag v-if="item.method === 'POST' " color="blue">{{item.method}}</a-tag>
    <a-tag v-if="item.method === 'PUT' " color="cyan">{{item.method}}</a-tag>
    <a-tag v-if="item.method === 'DELETE' " color="red">{{item.method}}</a-tag>
    <span>{{item.name}}</span>
  </router-link>
</template>

<script>
export default {
  props: {
    item: Object
  },
  data() {
    return {};
  },
  computed:{
    enableVersion(){
        return this.$store.state.globals.enableVersion;
    }
  }
};
</script>

<style lang="stylus" scoped></style>