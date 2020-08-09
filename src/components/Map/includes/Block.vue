<template>
  <div
    class="block-item disable-select"
    :class="blockType"
    @mouseenter="clickedBlock($event)"
    @click="clickedBlock($event)"
    @mousedown="clickedBlock($event)"
  >{{item.type}}</div>
</template>

<script>
export default {
  props: {
    item: Object,
    inputType: String
  },
  computed: {
      blockType() {
          if (this.item.type === 'empty') {
              return '';
          }
          return this.item.type.toLowerCase();
      }
  },
  methods: {
    clickedBlock(event) {
      if (event.buttons || event.type === 'click') {
        this.item.type = this.inputType;
      }
      // this.item.type = 'desk'
    },
  },
};
</script>

<style lang="scss" scoped>
</style>