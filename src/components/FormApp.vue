<template>
  <form class="form-app" @submit.prevent="register">
    <h1>Novo registro</h1>

    <div>
      <label class="label-form">Nome completo</label>
      <input
        v-model="name"
        placeholder="ex. Willian Brusch"
        class="form-app-input"
      />
    </div>

    <div>
      <label class="label-form">Data de nascimento</label>
      <Datepicker
        v-model="date"
        placeholder="ex. 07/04/92"
        textInput
        :format="format"
        :flow="flow"
      />
    </div>

    <button class="button-form" type="submit">Cadastrar</button>
  </form>
</template>

<script>
import { ref } from "vue";
import Datepicker from "@vuepic/vue-datepicker";
import "@vuepic/vue-datepicker/dist/main.css";

export default {
  name: "FormApp",
  components: { Datepicker },

  data() {
    return {
      name: "",
      allRegisters: [],
      allRegisterWithAge: [],
    };
  },

  setup() {
    const date = ref();
    const flow = ref(["year", "month", "calendar"]);
    const format = (date) => {
      const day = date.getDate();
      const month = date.getMonth() + 1;
      const year = date.getFullYear();

      return `${day}/${month}/${year}`;
    };

    return {
      date,
      flow,
      format,
    };
  },

  methods: {
    register() {
      if (this.name && this.date) {
        const age = this.discoverAge(this.date);

        this.allRegisters.push({
          name: this.name,
          born_date: this.date,
          age,
        });

        this.name = "";
        this.date = "";
      }
    },

    discoverAge(born_date) {
      const decreaseDates = new Date() - new Date(born_date);
      console.log(decreaseDates);
      return Math.floor(decreaseDates / 1000 / 60 / 60 / 24 / 365);
    },
  },
};
</script>

<style>
.form-app {
  width: 500px;
  height: 400px;
  padding: 50px;

  display: flex;
  flex-direction: column;
  justify-content: space-between;

  background: white;
  border-left: 10px solid var(--primaryBlue);
}

@media (max-width: 520px) {
  .form-app {
    width: 100vw;
    border-radius: 0px;
    border-left: none;
    border-bottom: 1px solid var(--primaryBlue);
    border-top: 1px solid var(--primaryBlue);
  }

  .label-form {
    font-size: 18px;
  }
}

.form-app-input {
  width: 392px;
  height: 38px;

  font-size: 16px;

  margin: 0px;
  padding: 0px;
  border-radius: 4px;
  border: 1px solid #e5e5e5;
  outline: #a3a3a3;
}

.form-app-input:hover {
  border-color: #a3a3a3;
  transition: 0.5s;
}

.form-app-input::placeholder {
  color: #a3a3a3;
  font-weight: 500;
  padding-left: 10px;
}

.form-app-input:active {
  color: #a3a3a3;
}

@media (max-width: 520px) {
  .form-app-input {
    width: 100%;
  }
}

.label-form {
  margin: 0;
  padding: 0;
  font-size: 14px;
  font-weight: 700;
  color: var(--primaryBlue);
}

.button-form {
  font-size: 18px;
  font-weight: 700;
  padding: 10px;
  border-radius: 4px;

  background-color: var(--primaryBlue);
  border: none;
  color: white;
}

.button-form:hover {
  background-color: var(--secondaryBlue);
  transition: 0.4s;
}

.button-form:active {
  background-color: var(--tertiaryBlue);
  filter: blur(1px);
  transition: 0.4s;
}
</style>
