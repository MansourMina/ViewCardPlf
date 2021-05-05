<template>
  <div>
    <img :src="emp.picture.large" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title text-center text-uppercase">
        {{ emp.name.title }} {{ emp.name.first }} {{ emp.name.last }}
      </h5>
      <ul class="list-group list-group-flush">
        <li class="list-group-item">{{ emp.email }}</li>
        <li class="list-group-item">{{ emp.dob.age }}</li>
        <li class="list-group-item">{{ emp.gender }}</li>
        <li class="list-group-item">{{ emp.phone }}</li>
      </ul>
      <ButtonHide @hihi="hihi()" />
    </div>
  </div>
</template>

<script>
import ButtonHide from '@/components/ButtonHide.vue';
export default {
  props: {
    emp: {
      type: Object,
    },
  },
  components: {
    ButtonHide,
  },
  methods: {
    hihi() {
      this.emp.visible = false;
    },
  },
};
</script>

<style lang="scss" scoped></style>
