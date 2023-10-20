<script setup>

    const props = defineProps(["tarefasFiltradas"])

</script>

<template>
    <ul v-if="tarefasFiltradas.length > 0" class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefasFiltradas">
        <input @change="(evento) => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
        <label :class="{done: tarefa.finalizada}" class="ms-3" :for="tarefa.titulo">
            {{tarefa.titulo}}
        </label>
        </li>
    </ul>
    <div v-else class="py-5">
        <h2 class="text-center">Sem tarefas pendentes</h2>
    </div>
</template>

<style scoped>
    .done{
        text-decoration: line-through;
    }
</style>