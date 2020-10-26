<template>
  <b-container fluid>
    <b-row>
      <h1>{{ title }}</h1>
    </b-row>
    <b-row class="lista">
      <b-row :key="tarefa.id" v-for="tarefa in tarefas" :id="tarefa.id">
        <b-col v-if="tarefa.estaCompleta">
          <b-card class="statusTrue" :title="tarefa.descricao"> </b-card>
        </b-col>
        <b-col v-else>
          <b-card class="statusFalse" :title="tarefa.descricao"> </b-card>
        </b-col>
      </b-row>
    </b-row>
  </b-container>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

export default {
  name: "App",
  data() {
    return {
      title: "Lista de Tarefas",
      tarefas: [
        { id: 1, descricao: "Limpar a casa", estaCompleta: true },
        { id: 2, descricao: "Lavar o carro", estaCompleta: false },
        { id: 3, descricao: "Estudar inglês", estaCompleta: true },
        { id: 4, descricao: "Visitar a vó", estaCompleta: true },
        { id: 5, descricao: "Passar com o cachorro", estaCompleta: false },
        { id: 6, descricao: "Comprar presente para amiga", estaCompleta: true },
      ],
    };
  },
};
</script>

<style>
body {
  font-family: "Quicksand", sans-serif;
  margin-top: 40px;
}

.row {
  justify-content: center;
  text-align: center;
}

.lista {
  display: flex;
  flex-wrap: initial;
  justify-content: space-evenly;
}

.statusTrue {
  background-color: #358548;
}

.statusFalse {
  background-color: #d11507;
}
</style>
