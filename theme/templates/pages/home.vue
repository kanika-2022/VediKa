<template>
  <div class="home-cont" :style="global_config ? 'color:' + global_config.props.text_body_color : ''">
    <sections page="home" />
    <!-- <applicationBanner /> -->
    <!-- <my-button></my-button> -->
  </div>
</template>
<style scoped lang="less">

.content,
.view {
  max-width: none !important;
  display: flex;
  flex-direction: column;
  width: 100%;
  margin: 0 !important;
}
</style>

<script>
// import shippingPolicy from '../../sections/shipping-policy.vue';
export default {
  data() {
    return {};
  },
  components: {
    // 'my-button':shippingPolicy
  },
};
</script>
