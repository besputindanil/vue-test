<template>
    <div class="name-input">
        <h2>Введите имя</h2>
        <input class="name-input" v-model='name' @keydown.enter="onNameInputEnter" type="text">
    </div>
    
    
</template>

<script>
export default {
    name: 'NameInput',
    data: function() {
        return {
            name: ''
        }
    },
    methods: {
        onNameInputEnter: function() {
            this.$emit('onNameInputEnter', this.name);
            this.name = ''
        }
     }
    
}
</script>

<style scoped>
.name-input {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 20px;
}
</style>
