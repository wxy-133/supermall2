<template>
<div class="tar-bar-item" @click="itemClick">
  <div v-if="!isActive">
    <slot name='item-icon'> </slot>
  </div>
  <div v-else>
    <slot name="itme-icon-active"></slot>
  </div>
  <div :style="activeStyle">
    <slot name='item-text'></slot>
  </div>
</div>
</template>

<script>
export default {
  name: "TarBarItem",
  props: {
    path: String,
    activeColor: {
      type: String,
      default: "red"
    }
  },
  data() {
    return {
      // isActive:true
    };
  },

  components: {},

  computed: {
    isActive() {
      return this.$route.path.indexOf(this.path) !== -1
    },
    activeStyle() {
      return this.isActive ? {
        color: this.activeColor
      } : {}
    }
  },

  beforeMount() {},

  mounted() {},

  methods: {
    itemClick() {
      this.$router.replace(this.path)
    }
  },

  watch: {}
};
</script>

<style scoped>
.tar-bar-item {
  flex: 1;
  text-align: center;
  line-height: 20px;
  padding: 10px 0px;
}

.tar-bar-item img {
  width: 24px;
  height: 24px;
  display: block;
  margin: 0 auto;
}
</style>
