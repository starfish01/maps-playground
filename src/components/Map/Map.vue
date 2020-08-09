<template>
  <div id="map" class="mapp">
    <div class="controller">
      <section>
        <div class="block">
          <b-radio
            v-for="(component, index) in buildingComponents"
            :key="index"
            v-model="inputType"
            name="name"
            :native-value="component.title"
          >{{component.title}}</b-radio>
        </div>
      </section>
    </div>
    <div class="p-10">
      <b-icon pack="fas" icon="arrow-up" size="is-small"></b-icon>
      <b-icon pack="fas" icon="arrow-down" size="is-small"></b-icon>
    </div>
    <div class="blocks">
      <Block v-for="(item, index) in items" :key="index" :item="item" :inputType="inputType" />
    </div>
    <div class="p-10">
      <b-icon pack="fas" icon="arrow-up" size="is-small"></b-icon>
      <b-icon pack="fas" icon="arrow-down" size="is-small"></b-icon>
    </div>
  </div>
</template>

<script>
import Block from "@/components/Map/includes/Block.vue";

export default {
  components: {
    Block,
  },
  data() {
    return {
      items: [],
      inputType: "Desk",
      buildingComponents: [
        {
          title: "Empty",
        },
        {
          title: "Desk",
        },
        {
          title: "Wall",
        },
        {
          title: "Door",
        },
      ],
    };
  },
  methods: {
    doSomething(item) {
      console.log(item.id);
    },
  },
  created() {
    // build array of items
    // 20/20?
    for (let i = 0; i < 20 * 15; ++i) {
      this.items.push({ id: i, type: "empty" });
    }

    console.log("fff");
  },
};
</script>

<style lang="scss" scoped>
</style>