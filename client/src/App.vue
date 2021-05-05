<template>
  <div id="app">
    <div class="d-block text-center ">
      <button
        type="button"
        style="background-color:black; color:white"
        class="btn  m-3 "
        @click="getEmployee()"
      >
        GET EMPLOYEES!
      </button>

      <div class="d-block text-center" v-for="s of showFalse" :key="s.phone">
        <button
          type="button "
          style="color:black"
          class="btn btn-primary d-block mx-auto w-50 m-3"
          @click="s.visible = true"
        >
          {{ s.name.first }} {{ s.name.last }}
        </button>
      </div>
    </div>
    <ViewCards :cards="employees" />
  </div>
</template>

<script>
import ViewCards from '@/components/ViewCards.vue';
import axios from 'axios';
export default {
  name: 'App',
  data() {
    return {
      employees: [],
    };
  },
  computed: {
   
    showFalse() {
      return this.employees.filter((el) => el.visible == false);
    },
  },
  methods: {
    async getEmployee() {
      const { data } = await axios({
        url: 'http://localhost:3000/employees',
        method: 'GET',
      });
      this.employees = data.map((el) => ({ visible: true, ...el }));
    },
  },
  components: {
    ViewCards,
  },
};
</script>

<style></style>
