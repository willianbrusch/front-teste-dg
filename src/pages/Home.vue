<template>
  <HeaderApp />
  <div class="container-app">
    <FormApp />
    <PersonsTable />
  </div>
</template>

<script>
import FormApp from "../components/FormApp.vue";
import PersonsTable from "../components/PersonsTable.vue";
import HeaderApp from "../components/HeaderApp.vue";

export default {
  name: "App",
  components: {
    FormApp,
    PersonsTable,
    HeaderApp,
  },
};
</script>

<style>
.container-app {
  padding-top: 30px;

  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  flex-wrap: wrap;
}
</style>
