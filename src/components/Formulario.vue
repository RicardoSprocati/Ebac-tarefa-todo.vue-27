<script setup>
    const props = defineProps(['cadastrarTarefa', 'tarefaTemporaria', 'trocarFiltro', 'editaTarefaTemp'])
</script>

<template>
    <form class="row" @submit.prevent="props.cadastrarTarefa">
        <div class="col">
            <input :value="props.tarefaTemporaria" @change="$props.editaTarefaTemp"
                required type="text" placeholder="Digite aqui a descrição da tarefa" class="form-control">
        </div>
        <div class="col-md-2">
            <button type="submit" class="btn btn-primary">Cadastrar</button>
        </div>
        <div class="col-md-2">
            <select @change="$props.trocarFiltro" class="form-control">
                <option value="todas">Todas tarefas</option>
                <option value="pendentes">Pendentes</option>
                <option value="finalizadas">Finalizadas</option>
            </select>
        </div>
    </form>
</template>