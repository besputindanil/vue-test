<template>
    <div>
        <button @click="onRandomButtonClick(names)">Кто кому дарит подарки!</button>
        <div>
            
        </div>
    </div>
</template>

<script>
export default {
    name: 'RandomName',
    props: {names: Array},
    data: function() {
        return {
            sortNames: []
        }
    },
    methods: {
        onRandomButtonClick: function(names) {
            const copyNames = [...names]
            const sortNames = copyNames.sort(() => Math.random() - 0.5);
            console.log(sortNames);
        }
    }
}
</script>
