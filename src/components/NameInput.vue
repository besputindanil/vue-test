<template>
    <div class="name-input">
        <h2>Введите имя</h2>
        <input class="name-input" v-model='name' @keydown.enter="onNameInputEnter" type="text">
    </div>
    
    
</template>

<script>
export default {
    name: 'NameInput',
    data() {
        return {
            name: ''
        }
    },
    methods: {
        onNameInputEnter() {
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

.name-input h2 {
    margin-top: 0;
    margin-bottom: 15px;

    text-transform: uppercase;
}

.name-input input {
    padding: 10px 15px;

    color: #5D0F4C;

    border: none;
    outline: 1px solid #306E12;
}

.name-input input:hover,
.name-input input:focus {
    outline-width: 2px;
}
</style>
