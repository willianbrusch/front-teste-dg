<template>
  <div class="persons-table">
    <div class="persons-table-header">
      <h3>Nome</h3>
      <h3>Idade</h3>
      <div class="persons-table-header-edit-close"></div>
    </div>
    <div>
      <PersonCard
        v-for="person in persons"
        :key="person.name"
        :personInfo="person"
      />
    </div>
    
  </div>
</template>

<script>
import PersonCard from "./PersonCard.vue";

export default {
  name: "PersonsTable",
  components: {
    PersonCard,
  },
  data() {
    return {
      persons: [
        {
          name: "Osvaldo Braga lala ospas",
          born_date: "2000-07-19T14:22:42.663Z",
          age: 26,
        },
        {
          name: "Luiz Augusto Santos",
          born_date: "2005-07-19T14:22:42.663Z",
          age: 12,
        },
        {
          name: "Osvaldo Braga",
          born_date: "1987-07-19T14:22:42.663Z",
          age: 57,
        },
      ],
    };
  },
};
</script>

<style>
.persons-table {
  width: 100vw;
  padding: 10px;
  margin-top: 50px;
  padding-bottom: 30px;

  background-color: white;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.persons-table-header {
  width: 68vw;
  padding: 10px;

  display: flex;
  justify-content: space-between;
}

.persons-table-header-edit-close {
  width: 110px;
}

@media (max-width: 1000px) {
  .persons-table {
  }
}

@media (max-width: 520px) {
  .persons-table {
    width: 100vw;
    font-size: 18px;
    border-radius: 0px;
  }
  .persons-table-header {
    width: 90vw;
  }
}
</style>
