<template>
  <div class="item">
    <p class="item__title">{{title}}</p>
    <button class="item__delete-button" @click="$emit('remove',number)">Удалить</button>
  </div>
</template>

<script setup>
import {defineProps, toRefs} from "vue"

const props = defineProps({
    title: String,
    number: Number,
});

const {title, number} = toRefs(props);

</script>

<style>
.item{
    display: flex;
    margin: 10px;
    border: 1px solid silver;
    border-radius: 6px;
    width: 400px;
    justify-content: space-between;
    padding: 10px;
}
</style>