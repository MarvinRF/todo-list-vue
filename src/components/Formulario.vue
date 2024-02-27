<script setup>
const props = defineProps([
  "cadastraTarefa",
  "tarefaTemp",
  "trocarFiltro",
  "editaTarefaTemp",
]);
</script>

<template>
  <form @submit.prevent="props.cadastraTarefa">
    <div class="row">
      <div class="col">
        <input
          required
          :value="props.tarefaTemp"
          @change="props.editaTarefaTemp"
          type="text"
          placeholder="digite a descrição da tarefa"
          class="form-control"
        />
      </div>
      <div class="col-md-2">
        <button type="submit" class="btn btn-primary">Cadastrar</button>
      </div>
      <div class="col-md-3">
        <select class="form-control" @change="props.trocarFiltro">
          <option value="todas">Todas as tarefas</option>
          <option value="pendentes">Tarefas pendentes</option>
          <option value="finalizadas">Tarefas concluidas</option>
        </select>
      </div>
    </div>
  </form>
</template>
