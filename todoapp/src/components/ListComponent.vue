<template>
    <div class="action-panel">
        <input type="text" v-model="inputText">
        <button class="action-panel__add-button" @click="addElement">Добавить</button>
    </div>
    <div class="list">
        <ItemComponent @remove="removeElement" v-for="(item, i) in todoList" :title="item" :number="i" :key="i"/>
    </div>
</template>

<script setup>
import ItemComponent from './ItemComponent.vue'
import {ref} from "vue"

const todoList = ref([
    'Задача 1',
    'Задача 2',
    'Задача 3',
]);

const inputText = ref("");

const addElement = () => {
    todoList.value.push(inputText.value);
    inputText.value = "";
}

const removeElement = (elementIndex) => {
    todoList.value.splice(elementIndex,1);
}
</script>

<style>
.list{
    background-color: #9E9E9E;
    width: fit-content;
    padding: 10px;
}
.action-panel{
    padding: 10px;
}
</style>