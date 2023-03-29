<template>
  <span>
    <my-icon v-if="item.icon" :type="item.icon"></my-icon>
    <a-badge v-if="enableVersion&&item.hasNew" status="processing" title="新接口" style="margin-bottom:3px;" />
    <span>{{item.name}}</span>
  </span>
</template>

<script>
export default {
  props: {
    item: Object,
    collapsed: {
      type: Boolean,
      default: false
    }
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