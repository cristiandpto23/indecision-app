<script>
export default {
    props: {
        title: {
            type: String,
            default: 'Counter',
        },
        start: {
            type: Number,
            default: 100,
            validator(value) {
                return value > 100 ? true : false;
            }
        },
    },
    name: 'Counter',
    data() {
        return {
            counter: this.start,
        };
    },
    methods: {
        getSquareValue() {
            console.log('getSquareValue');
            return this.counter * this.counter;
        },
        // increase
        increase() {
            console.log('increase');
            // this.counter++;
            this.counter = this.counter + 1;
        },
        //decrease
        decrease() {
            console.log('decrease');
            this.counter--;
        },
    },
    computed: {
        squareCounter() {
            console.log('computed squareCounter');
            return this.counter * this.counter;
        },
        customTitle() {
            return this.title ? this.title : 'Counter';
            // if (!this.title) {
            //     return 'Counter';
            // } else {
            //     return this.title;
            // }
        },
    },
};
</script>

<template>
    <h2>{{ customTitle }}</h2>
    <p>{{ counter }} <sup>2</sup> = {{ squareCounter }}</p>
    <div>
        <button @click="increase()">+1</button>
        <button @click="decrease()">-1</button>
    </div>
</template>

<style scoped>
button {
    background-color: #64bb87;
    border-radius: 5px;
    border: 1px solid white;
    box-shadow: 2px 2px 3px rgba(0, 0, 0, 0.2);
    color: white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;
}

button:hover {
    background-color: #5aa67b;
    transition: 0.3s ease-in-out;
}
</style>
