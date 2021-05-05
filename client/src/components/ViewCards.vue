<template>
  <div class="d-flex flex-wrap  justify-content-center">
    <div
      class="card m-3"
      style="width: 18rem;"
      v-for="e of showTrue"
      :key="e.phone"
    >
      <ViewCard :emp="e" />
    </div>
  </div>
</template>

<script>
import ViewCard from '@/components/ViewCard.vue';
export default {
  props: {
    cards: {
      type: Array,
    },
  },
  computed: {
    showTrue() {
      return this.cards.filter((el) => el.visible == true);
    },
  },
  components: {
    ViewCard,
  },
};
</script>

<style lang="scss" scoped></style>
