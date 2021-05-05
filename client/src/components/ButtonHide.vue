<template>
  <div>
    <button
      type="button "
      style="color:black"
      class="btn btn-outline-primary d-block mx-auto my-3  m-3"
      @click="tellHideCard()"
    >
      HIDE CARD
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    tellHideCard(aha) {
      this.$emit('hihi', aha);
    },
  },
};
</script>

<style lang="scss" scoped></style>
