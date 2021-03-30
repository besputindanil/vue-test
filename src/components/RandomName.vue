<template>
    <div class="random-name">
        <button class="random-name__button button" @click="onRandomButtonClick">Кто кому дарит подарки!</button>
        <ul class="app-list random-name__list">
            <li class="random-name__item" v-for="(name, i) in sortNames" :key="i">
                {{ name[0] }} дарит подарок {{ name[1] }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'RandomName',
    props: {names: Array},
    data() {
        return {
            sortNames: []
        }
    },
    methods: {
        onRandomButtonClick() {
            this.sortNames = [];
            const copyNames = [...this.names]
            let tempArr = [];
            for (let i = copyNames.length; i > 0; i--) {
                let randomInd = Math.floor(Math.random() * i)
                let randomName = copyNames.splice(randomInd, 1)[0];
                tempArr.push(randomName);
            }
            tempArr = [...tempArr, tempArr[0]]
            
            for (let j = 0; j < tempArr.length - 1; j++) {
                this.sortNames.push([tempArr[j], tempArr[j + 1]])
            }
            return this.sortNames
        }
    }
}
</script>
