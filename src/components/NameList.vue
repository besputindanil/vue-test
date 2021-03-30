<template>
    <div class="name">
        <button class="name__button button" @click="onClearList">Очистить список</button>
        <ul class="app-list name__list">
            <li class="name__item" v-for="(name, index) in names" :key="index">
                {{ name }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Name',
    props: {names: Array},
    methods: {
        onClearList() {
            this.$emit("onClearList");
        }
    }
}
</script>

<style scoped>
.name {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    margin-right: 50px;
}
</style>