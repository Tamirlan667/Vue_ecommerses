<template>
  <base-button variant="contained" mode="primary" @click="loadMore"
    >Show more</base-button
  >
</template>

<script>
import BaseButton from "./UI/Buttons/BaseButton.vue";
export default {
  components: { BaseButton },
  props: {
    count: {
      type: Number,
      required: true,
    },
    listLength: {
      type: Number,
      required: true,
    },
  },

  data() {
    return {
      itemsCountToShow: this.count,
    };
  },

  methods: {
    loadMore() {
      if (this.count > this.listLength) return;

      this.itemsCountToShow += this.count;
      this.$emit("onShowMoreClick", this.itemsCountToShow);
    },
  },
};
</script>

<style></style>
