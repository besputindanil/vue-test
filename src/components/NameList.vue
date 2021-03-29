<template>
    <ul class="name-list">
        <li class="name-item" v-for="(name, index) in names" :key="index">
            {{ name }}
        </li>
    </ul>
</template>

<script>
export default {
    name: 'Namelist',
    props: {names: Array}
}
</script>

<style scoped>
.name-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 0;
    margin-bottom: 20px;
    padding-left: 0;

    list-style: none;
}
</style>